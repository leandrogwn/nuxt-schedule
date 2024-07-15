<template>
    <!-- Listagem dos cantatos-->
    <div class="w-full px-2">
        <!-- Item contato-->
        <ListItem v-for="contact in contacts" :key="contact.id">
            {{ contact.name }}
            <template #actions>
                <button @click="editContact(contact.id)">Editar</button>
                <button @click="removeContact(contact.id)">Excluir</button>
            </template>
        </ListItem>
    </div>

    <UIButton @click="addContact">Adicionar Contato</UIButton>
</template>

<script setup>
const router = useRouter();
const { contactList, deleteContact } = useContacts();
const contacts = contactList();

const addContact = () => {
    router.push("/form");
};

const editContact = (id) =>{
    router.push({ path: '/form', query:{id}});
};

const removeContact = (id) => {
    deleteContact(id)
}

</script>
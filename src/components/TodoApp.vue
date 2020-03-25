<template>
    <div id="container">
        <div id="to-do">
            <div id="nowe-todo">
                <p>Nowe to-do: {{ newItem }}</p>
                <v-text-field class="text-input" outlined
                              placeholder="todo"
                              v-model="newItem"></v-text-field>
                <v-btn v-on:click="addItem">Dodaj</v-btn>

            </div>
            <div id="items">
                <h2 class="item"
                    v-bind:class="{
       completed: item.completed
       }"
                    v-for="item in items"
                    v-bind:key="item.title">
                    {{ item.title }}
                    <v-btn v-if="!item.completed" v-on:click="removeItem(item.id)">Zrobione</v-btn>
                </h2>
            </div>
        </div>
    </div>
</template>
<style scoped src="@/assets/style/style.css"></style>
<script>

    export default {
        name: 'App',

        data(){
            return {
                newItem:'default', //dodaje tekst z pola tekstowego
                items: [ //robi nam tablice
                    { title: 'Zrobić zakupy', completed: false, id: '3232'},
                    { title: 'Nagrać kurs', completed: true, id: '33323'}
                ]
            }
        },
        methods: { //metody,funkcje
            addItem(){ //pushuje nam obiekt do tablicy
                this.items.push({
                    title: this.newItem,
                    completed: false,
                    id: Math.random()
                })
                this.newItem = '' // czyści to-do
            },
            removeItem(id){
                const index = this.items.findIndex(el => el.id === id)
                this.items[index].completed = true
            },

        }
    };

</script>

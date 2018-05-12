<template>

<v-layout>
    <v-flex text-xs-center>
        <v-form>
            <v-text-field label="Nombre del libro" v-model="user.bookname"></v-text-field>
            <v-text-field label="Url del libro" v-model="user.urlLibro"></v-text-field>
            <v-text-field label="Url del libro" v-model="user.urlPortada"></v-text-field>
            <v-btn
              @click="submit"
            >
              submit
            </v-btn>
        </v-form>
        <v-btn
          @click="fetchData"
        >
          get data
        </v-btn>
        <ul class="list-group">
              <li class="list-group-item" v-for="u in users" :key="u.bookname">{{ u.bookname }} - {{ u.urlLibro }} - {{ u.urlPortada }}</li>
          </ul>
    </v-flex>
</v-layout>

</template>

<script>

export default {
    data() {
            return {
                user: {
                    bookname: '',
                    urlLibro: '',
                    urlPortada: ''
                },
                users: [],
                resource: {},
                node: 'data'
            }
        },
        methods: {
            submit() {
                    //                    this.$http.post('data.json', this.user)
                    //                        .then(response => {
                    //                            console.log(response);
                    //                        }, error => {
                    //                            console.log(error)
                    //                        });
                    //this.resource.save({}, this.user);
                    this.resource.saveAlt(this.user);
                },
                fetchData() {
                    this.resource.getData({
                            node: this.node
                        })
                        .then(response => {
                            return response.json();
                        })
                        .then(data => {
                            const resultArray = [];
                            for (let key in data) {
                                resultArray.push(data[key]);
                            }
                            this.users = resultArray;
                        });
                }
        },
        created() {
            const customActions = {
                saveAlt: {
                    method: 'POST',
                    url: 'data.json'
                },
                getData: {
                    methid: 'GET'
                }
            };
            this.resource = this.$resource('{node}.json', {}, customActions);
        }
}

</script>

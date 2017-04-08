<template>
    <div>
        <div class="text-center">
            <button class="btn btn-success" @click="onGetQuotes">
                Get Quotes
            </button>
        </div>
        <hr>

        <app-quote v-for="quote in quotes" :qt="quote" @quoteDeleted="onQuoteDeleted($event)"></app-quote>
    </div>
</template>

<script type="text/babel">
    import Quote from './quote.vue';
    import axios from 'axios';
//    const serverUrl = 'http://localhost:8000';
    const serverUrl = 'http://localhost/backend-scotch-app/public/';
    export default {
        mounted: function(){
                axios.get(serverUrl + '/api/quotes')
                        .then((response) => {
                    this.quotes = response.data.quotes;
                })
            .catch((error) => {
                    console.log(error)
                });
        },

        data() {
            return {
                quotes: []
            }
        },
        methods: {
            onGetQuotes() {
                 axios.get(serverUrl + '/api/quotes')
                         .then((response) => {
                    this.quotes = response.data.quotes;
                })
                .catch((error) => {
                    console.log(error)
                });
            },
            onQuoteDeleted(id) {
                const position = this.quotes.findIndex((element) => {
                    return element.id == id;
                });
                this.quotes.splice(position, 1);
            }
        },
        components: {
            'app-quote' : Quote
        }
    }
</script>
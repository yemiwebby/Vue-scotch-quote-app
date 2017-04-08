<template>
    <div>
        <div class="col-lg-6 col-md-6 col-sm-6 col-xs-12">
            <form @submit.prevent="onSubmitted">
                <div class="form-group">
                    <label for="content"><b>Quote</b></label><br>
                    <i> Write your quote</i>
                    <br><br>
                    <input
                            type="text"
                            name=""
                            id="content"
                            class="form-control"
                            v-model="quoteContent">
                </div>

                <div class="form-group">
                    <button type="submit" class="btn btn-success">
                        Submit
                    </button>
                </div>
            </form>
        </div>
    </div>
</template>

<script type="text/babel">
    import axios from 'axios';
//    const serverUrl = 'http://localhost:8000';
    const serverUrl = 'http://localhost/backend-scotch-app/public/';
    export default {
        data() {
            return {
                quoteContent: ''
            }
        },

        methods: {
            onSubmitted() {
                axios.post(serverUrl + '/api/quote',
                        {content: this.quoteContent})
                        .then((response) => {
                    console.log(response);
                    window.location.href = "/";
                })
                .catch ((error) => {
                    console.log(error)
                });
            }
        }
    }
</script>
<script>
    import axios from 'axios';
    export default { 
        data() {
            return {
                moods: ['Happy', 'Sad', 'Angry'],
                subject: "",
                entry: '',
                selMood: ''
            }
        },
        methods: {
            async addPost() {
                try {
                    await axios.get('http://localhost/WAD2/week10/blog/addPost.php', { params: {
                        'subject': this.subject,
                        'entry': this.entry,
                        'mood': this.selMood
                    }});
                } catch (error) {
                    console.log(error);
                }
            }
        }
    }
</script>

<template>
    <div class="table m-2">
        <h3>Add a New Blog Post</h3>

        Subject: <input type='text' size='30' v-model='subject' required>
        <br>

        Entry: <br>
        <textarea name='entry' cols='80' rows='5' v-model='entry' required></textarea>
        <br>

        Mood:
        <!-- TODO: Build a dropdown list here for selecting the mood -->
        <select v-model="selMood">
            <option v-for="mood in moods">
                {{ mood }}
            </option>
        </select>
        <br>

        <br>
        <button @click="addPost">Submit New Post</button>

        <hr> Click  <router-link to="/ViewPosts/">here</router-link>  to return to Main Page
       
    </div>
</template>




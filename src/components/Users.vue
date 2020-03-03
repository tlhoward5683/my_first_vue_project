<template>
    <div>
        <table class="userTable">
            <thead>
                <tr>
                    <th class="userHeader">ID</th>
                    <th class="userHeader">Name</th>
                    <th class="userHeader">Last Login</th>
                    <th class="userHeader">Login Count</th>
                    <th class="userHeader">Project Count</th>
                </tr>
            </thead>
            <tbody v-bind:key="user.id" v-for="user in usersData">
                <User v-bind:user="user" v-bind:rowColor=getRowColor(user) />
            </tbody>
        </table>
    </div>
</template>

<script>
import User from './User'

export default {
    name: "Users",
    components: {
        User
    },
    props: ["rowColor"],
    data() {
        return {
            usersData: [
                {"id": 0, "username": "ana", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 0, "project_count": 12 },
                {"id": 1, "username": "tim", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 23, "project_count": 234 },
                {"id": 23, "username": "kyle", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 4, "project_count": 2354 },
                {"id": 34, "username": "alex", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 0, "project_count": 6563 },
                {"id": 234, "username": "glenn", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 1, "project_count": 3452 },
                {"id": 633, "username": "cort", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 1000, "project_count": 2345 },
                {"id": 693, "username": "sean", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 3, "project_count": 8654 },
                {"id": 623, "username": "violet", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 0, "project_count": 4028 },
                {"id": 665, "username": "nik", "last_login": "2019-08-20T22:15:09.926Z", "login_count": 0, "project_count": 4428 }
            ],
        }
    },
    methods: {
        getRowColor: function(user) {
            if (this.rowColor === 'greenRow' && user.login_count >= 1) {
                // login count greater than or equal to 1 should have a green background
                return "greenRow";
            } else if (this.rowColor === 'redRow' && user.login_count === 0) {
                // login count of 0 should have a red background
                return "redRow";
            } else {
                return "whiteRow";
            }
        }
    }
}
</script>

<style scoped>
    .userTable {
        text-align: left;
        border-collapse: collapse;
        margin: 50px;
    }
    .userHeader {
        padding: 20px 50px;
        border: 1px solid #aaa;
        background-color: #ccc;
    }
</style>
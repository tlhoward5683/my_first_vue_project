<template>
    <tr>
        <td v-bind:class="compClasses">{{user.id}}</td>
        <td v-bind:class="compClasses">{{user.username}}</td>
        <td v-bind:class="compClasses">{{user.last_login}}</td>
        <td v-bind:class="compClasses">{{user.login_count}}</td>
        <td v-bind:class="compClasses">{{user.project_count}}</td>
    </tr> 
</template>

<script>
export default {
    name: "User",
    props: ["user", "rowColor"],
    computed: {
        compClasses: function() {
            return {
                whiteRow    : (this.rowColor === 'whiteRow'),
                redRow      : (this.rowColor === 'redRow'),
                greenRow    : (this.rowColor === 'greenRow')
            }
        }
    }
}
</script>

<style scoped>
    td {
        padding: 10px 50px;
        border: 1px solid #aaa;
    }
    .whiteRow {
        background-color: #fff;
        color: #333;
    }
    .greenRow {
        background-color: rgb(64, 112, 64);
        color: #fff;
    }
    .redRow {
        background-color: rgb(114, 0, 0);
        color: #fff;
    }
</style>

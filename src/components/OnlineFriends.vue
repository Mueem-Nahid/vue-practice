<template>
    <div>
        <h2>Online Friends</h2>
        <div v-for="(friend,index) in friends" :key="index">
            <h6 v-if="friend.isOnline">{{friend.name}}</h6>
        </div>
    </div>
</template>

<script>
export default {
    name: 'OnlineFriends',
    props: ['friends'],
    data() {
        return {

        }
    }
}
</script>

<style>
    
</style>
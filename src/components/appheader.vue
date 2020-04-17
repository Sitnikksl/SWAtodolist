<template>
    <div class="header">
        <div class="header-left">
            <div class="user-block">
                <div class="user-img"></div>
                <div class="user-name">{{ userName }}</div>
                <a href="#" class="log-out" v-on:click = 'logOut'></a>
            </div>
        </div>
        <div class="header-right">
            <div class="header-filter">
                <div class="filter">
                    <label for="">Фильтр:</label>
                    <select name="" id="">
                        <option>все</option>
                        <option>неисполненные</option>
                        <option>завершенные</option>
                    </select>
                </div>
                <div class="display-filter">
                    <label>Отображать:</label>
                    <select name="" id="">
                        <option>по дате</option>
                        <option>еще option</option>
                    </select>
                </div>
            </div>
        </div>
    </div>
</template>

<style>

</style>

<script>
export default {
    data(){
        return{
            userName: 'Mark'
        }
    },
    methods: {
        logOut: function(){
            this.$emit('event');
        }
    },
}
</script>

<style>
.header{
    display: flex;
    justify-content: space-between;
}
.user-block{
    display: flex;
    align-items: center;
}
.user-img{
    width: 69px;
    height: 69px;
    /* background-color: #000; */
    background-image: url('../assets/Vector-1.png');
    background-repeat: no-repeat;
    background-position: center;
}
.log-out{
    display: block;
    width: 69px;
    height: 69px;
    /* background-color: #000; */
    background-image: url('../assets/Group.png');
     background-repeat: no-repeat;
    background-position: center;
}
</style>
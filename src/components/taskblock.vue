<template>
    <div class="task-block">
        <a href="#" class="add-task" @click='showModal'></a>
        <div class="task-container">
            <ul>
                <li v-for='item in tasks' :key='item.task'>
                    <div href="#" class="task">
                        <div class="task-left" @click='showSub'>
                            <h3 class="task-name">{{item.task}}</h3>
                            <div class="task-bottom">
                                <p class="task-date">{{ item.date}}</p>
                                <div class="task-color"></div>
                            </div>
                        </div>
                        <div class="task-right">
                            <button class="add-new btn"></button>
                            <button class="edit btn"></button>
                            <button class="delete btn"></button>
                        </div>
                    </div>
                    <ul v-if="subVisible">
                        <li class="sub-task" v-for='temp in item.subtasks' :key='temp.subtask'>
                            <div class="sub-task__left">
                                <h4 class="sub-task__name">{{temp.subtask}}</h4>
                                <p class="urgency">Срочность: 
                                    <select>
                                        <option>1</option>
                                        <option>2</option>
                                        <option>3</option>
                                        <option>4</option>
                                        <option>5</option>
                                    </select>
                                </p>
                                <input type="checkbox">
                                <p class="task-date">{{ item.date}}</p>
                            </div>
                            <div class="sub-task__desc">
                                {{ item.desk }}
                            </div>
                            <div class="sub-task__right">
                                <button class="edit btn"></button>
                                <button class="delete btn"></button>
                            </div>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
        <div class="add-task-modal" v-if='modalVisible'>
            <input type="text" placeholder='Введите название задачи' ref="taskName" v-model="taskName">
            <input type="text" placeholder='Укажите срочность'>
            <textarea name="" id="" cols="30" rows="10" placeholder="Добавьте описание"></textarea>
            <button @click='addTask'>Добавить</button>
            <a href="#" class="close-btn" @click='close'></a>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
           tasks: [
               {task: 'Задача1',
                date: '10/04/2020',
                subVisible: true,
                subtasks: [
                    {
                        subtask: 'Подзадача 1'
                    },
                    {
                       subtask: 'Подзадача 2' 
                    }
                ],
                desk: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quidem, autem?'
               },
               {task: 'Задача2',
                date: '10/04/2020',
               },
               {task: 'Задача3',
                date: '10/04/2020',
                 subtasks: [
                    {
                        subtask: 'Подзадача 1'
                    },
                ],
               }
           ],
            taskName: '',
           modalVisible: false
        }
    },
    methods:{
        showSub: function(){
           this.subVisible = !this.subVisible;
           console.log(this.subVisible)
        },
        showModal: function(){
            this.modalVisible = !this.modalVisible;
        },
        close: function(){
            this.modalVisible = !this.modalVisible;
        },
        addTask: function(){
           this.tasks.push(this.taskName)
        }
    }
}
</script>

<style>
.task-block{
    display: flex;
    flex-direction: column;
    /* justify-content: center; */
    align-items: center;
}
    .task-container{
       
        /* border: 1px solid black; */
    }
    .add-task{
        display: block;
        width: 48px;
        height: 48px;
        background-image: url('../assets/add1.png');
        margin-top: 48px;
    }
    .task{
        margin: 0;
        font-family: Playfair Display;
        text-decoration: none;
        display: flex;
        justify-content: space-between;
        width: 920px;
        border-radius: 27px;
        background: #2B2B2B;
        margin-top: 30px;
        align-items: center;
    }
    .task:hover{
        text-decoration: underline;
    }
    .task-left{
        padding: 54px 0 31px 55px;
        cursor: pointer;
    }
    .task-right{
        margin-right: 44px;
    }
    .task-bottom{
        display: flex;
        align-items: center;
    }
    .task-name{
        font-style: normal;
        font-weight: normal;
        font-size: 70px;
        color: #C6B3A6;
    }
    .task-date{
        color: #C6B3A6;
    }
    .task-color{
        width: 46px;
        height: 46px;
        background: #151312;   
        border-radius: 5px;
        margin-left: 35px;
    }
    .btn{
        width: 48px;
        height: 55px;
        background-repeat: no-repeat;
        background-position: center;
        cursor: pointer;
    }
    .add-new{
        background-image: url('../assets/new 2.png');
    }
    .edit{
        background-image: url('../assets/Vector.png');
    }
    .delete{
        background-image: url('../assets/trash 2.png');
    }
    .sub-task{
        display: flex;
        width: 820px;
        margin: 0 auto;
        background: #BCBCBC;
        border-radius: 27px;
        margin-top: 31px;
        justify-content: space-between;
    }
    .sub-task__desc{
        width: 500px;
    }
    .sub-task .task-date{
        color: #000;
    }
    .sub-task__right{
        display: flex;
    }
    .add-task-modal{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        width: 600px;
        height: 300px;
        background-color: #fff;
        border-radius: 5%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .close-btn{
        width: 50px;
        height: 50px;
        display: block;
        background-image: url('../assets/trash 2.png');
    }
</style>
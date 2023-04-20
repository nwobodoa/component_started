<template>
    <div>
        <h1>Student Lists</h1>
        <ul v-if="items.length">
            <!-- conditional rendering using the if-statement and for loop -->
            <li v-for="item in items" :key="item.id">
            Student Detail: {{ item.fname }} {{ item.lname }} {{ item.program }}

            </li>
        </ul>
        <!-- {{ studentDetail.fname }} {{ studentDetail.lname }} {{ studentDetail.program }} -->
    </div>
</template>

<script>


import '../App.css';

export default{
    name: "EnrolList",
    props:{
        studentDetail:{
            fname:"",
            lname: "",
            program: ""
        }

    },

    data(){
        return{
            items:[]
        }
    },
    //watch will keep mointoring the studentDetail
    //once there is a change this method is called
    watch:{
        studentDetail(newStudent){
            //add new student to the items array
            this.items.push(newStudent);
            // this.item = [...this.items, new student];
        },
    }
}

</script>

<style></style>

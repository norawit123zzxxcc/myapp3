<!-- <template>
    <div>
    <img :src="picture" :width="size" :height="size"> 
    <p>ชื่อ : {{ firstname }}</p>
    <p>นามสกุล : {{ lastname }}</p>
    <p>อายุ : {{ age }}</p>
    <p>ที่อยู่ : <span v-html="address"></span></p>
    </div>
</template>

<script>
    export default {
    data(){
    return{
        firstname: "Norawit",
        lastname: "Seangrat",
        age: 18,
        address: "<i>Chonburi</i>",
        picture: "https://lh3.googleusercontent.com/a/AAcHTtcqHj3ngEg6N8sKsQd7HcnQaPox8ql_tD9HO306CZdH6LY=s360-c-no",
        size: 150
        }
    }
    }
</script> -->
<template>
    <div>
        <img :src="picture" :width="size" :height="size"> 
        <p>ชื่อ : {{ firstname }}</p>
        <p>นามสกุล : {{ lastname }}</p>
        <p>ชื่อเล่น : {{ nickname }}</p>
        <p>อายุ: {{ age }}</p>
        <p>ที่อยู่: <span v-html="address"></span></p> 
        <p v-if="hobby.length ===0">ไม่มีงานอดิเรก</p>
        <div v-else>
         <p>งานอดิเรก :</p>
            <ul>
                <li v-for="item in hobby">{{ hobby [0] }}</li>
            </ul>   
        </div>
            <p>ข้อมูลพื้นฐาน :</p>
            <ul>
                <li v-for="(value,key) in general" :key="key">{{ key }} : {{ value }}</li>
            </ul>
            <button @click="showData">คลิกเพื่อดูข้อมูล</button>
    </div>
</template>
    <script>
        export default {
        data(){
            return{
                firstname: "Norawit",
                lastname: "Seangrat",
                age: 18,
                address: "<i>Chonburi</i>",
                picture:"https://lh3.googleusercontent.com/a/AAcHTtcqHj3ngEg6N8sKsQd7HcnQaPox8ql_tD9HO306CZdH6LY=s360-c-no",
                size: 150,
                hobby : ["ทำไร่","ทำสวน"],
                general : {gender:"ชาย",weight:63.5,height:173.5,status:false},
                nickname : ''
             }   
     },
     methods:{
        getFullname(){
            return `$(this.firstname) $(this.lastname)` 
        },
        showData(){
            alert(this.firstname)
        },
        increment(value){
            this.age += value
        },
        decrement(value){
            this.age -= value
        },
        setNickname(event){
                this.nickname=event.target.value
            },
        submitForm(){
            alert('บันทึกข้อมูลเรียบร้อย')
        }
   }
}
    </script>
    

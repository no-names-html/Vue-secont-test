<template>
    <dir class="root">
        <p>Єба, це працює</p>
        <button type="button" @click="delValue">-</button>
        <input type='number' 
            :value=numbersOfXyu 
            @input='changeVal($event.target.value)'
            @change='verify($event.target.value)'/>
        <button type="button" @click="addValue">+</button>
        <p>{{numbersOfXyu}}</p>
    </dir>
</template>

<script>
export default {
    name: 'firstComponent',
    data(){     
        return{
            numbersOfXyu: 1
        }
    },
    methods: {
        addValue(){
            this.numbersOfXyu += 1 ;
        },
        delValue(){
            this.numbersOfXyu -= 1;
        },
        verify(val){
            if(val>10) this.numbersOfXyu = 10;
            else if(val<0) this.numbersOfXyu = 0;
        },
        changeVal(val){
            this.numbersOfXyu = val; 
        }
    }      
}
</script>
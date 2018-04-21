<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12">
                <br>
                <button @click="selectedColor = 'appBlue'" class="btn btn-primary">Load Blue Template</button>
                <button @click="selectedColor = 'appGreen'" class="btn btn-success">Load Green Template</button>
                <button @click="selectedColor = 'appRed'" class="btn btn-danger">Load Red Template</button>
                <hr>
             
                {{ selectedColor }}
                <keep-alive>
                   <component :is="selectedColor">
                   </component>    
                </keep-alive>
            </div>
        </div>
    </div>
</template>

<script>
    import Blue from './components/Blue.vue';
    import Green from './components/Green.vue';
    import Red from './components/Red.vue';

    export default {
        components: {
            appBlue: Blue,
            appGreen: Green,
            appRed: Red
        },
        data: function (){
            return {
                title: 'This is what you click!',
                selectedColor: ''
            }
        }
    }
</script>

<style>
</style>

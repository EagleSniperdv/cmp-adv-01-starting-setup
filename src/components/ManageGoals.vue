<template>
    <div>
        <h2>ManageGoals</h2>
        <input type="text" ref="goal">
        <button @click="setGoal">set Goal</button>
        <teleport to="body">
            <error-alert v-if="inputIsInvalid">
            <h2>Invalid Input</h2>
            <p>please enter goal...</p>
            <button @click="confirmError">Okay</button>
            </error-alert>
        </teleport>
    </div>
</template>

<script>
    import ErrorAlert from './ErrorAlert.vue';

    export default{

        components: {
            ErrorAlert,
        },

        data() {
            return {
                inputIsInvalid: false
            }
        },

        methods: {

            setGoal() {

                const enteredValue = this.$refs.goal.value;

                if (enteredValue === '') {
                    this.inputIsInvalid = true;
                } 
            },
            confirmError() {
                this.inputIsInvalid = false;
            }
        }
    }
</script>
<template>
    <div class="page-body flex">
        <form class="form-container flex" @submit="onSubmit">
            <div class="form-head flex">
                <img class="mytask-img" src="../../images/mytasklogo.png" alt="">
                <a href="#">www.mytask</a>
            </div>
            <div class="form-body">
                <h1>Login</h1>
                <p>Sign into your dashboard</p>
                <div class="form-control flex">
                    <label>Email Address</label>
                    <div class="input-wrap flex">
                        <input type="text" v-model="email" name="email" placeholder="Enter email" required>
                        <img src="../../images/at-regular-1.png" alt="" class="input-img">
                        <img class="focus-image" src="../../images/at-regular.jpg" alt="">
                    </div>
                </div>
                <div class="form-control flex">
                    <label>Password</label>
                    <div class="input-wrap flex">
                        <input type="text" v-model="password" name="password" placeholder="Enter password" required>
                        <img src="../../images/lock-regular.jpg" alt="" class="input-img">
                        <img class="focus-image" src="../../images/lock-regular-blue.png" alt="">
                    </div>
                    
                </div>
                <div class="button-container flex">
                    <input type="submit" value="Login" class="btn btn-block">
                    <a href="#">Forgot password?</a>
                </div>
                
                <p>Don't have an account? <a href="#">Request account</a></p>
            </div>
        </form>
        <div class="version">myTask v1.0</div>
    </div>
</template>

<script>
export default {
    name: 'Login',
    data() {
        return {
            email: '',
            password: '',
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault()

            const user = {
                email: this.email,
                password: this.password,
            }
            this.$emit('signIn', user)
            this.email = ''
            this.password = ''
        }
    }
}
</script>

<style scoped>
    
</style>
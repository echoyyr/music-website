<template>
    <div class="page-register">
        <article class="header">
            <header>
                <a href="" class="site-logo"></a>
                <span class="login">
                    <em class="blod">已有美团账号</em>
                     <a href="/login">
                       <el-button type="primary" size="small">登陆</el-button>
                     </a>
                </span>
            </header>
        </article>
        <section>
            <el-form ref="ruleform" :model="ruleform" :rules='rules'  label-width="100px">
                <el-form-item label="昵称" prop="name">
                    <el-input v-model="ruleform.name"></el-input>
                </el-form-item>
                <el-form-item label="邮箱" prop="email">
                    <el-input v-model="ruleform.email"></el-input>
                    <el-button size="mini" round @click="sendMsg">发送验证码</el-button>
                    <span class="status">{{msgStatus}}</span>
                </el-form-item>
                <el-form-item label="验证码" prop="code">
                    <el-input v-model="ruleform.code"></el-input>
                </el-form-item>
                <el-form-item label="密码" prop="pwd">
                    <el-input v-model="ruleform.pwd" type="password"></el-input>
                </el-form-item>
                <el-form-item label="确认密码" prop="cpwd">
                    <el-input v-model="ruleform.cpwd" type="password"></el-input>
                </el-form-item>
                <el-form-item>
                   <el-button type="primary" @click="register">同意以下协议并注册</el-button>
                    <div class="error">{{error}}</div>
                </el-form-item>
                <el-form-item>
                    <a class="f1" href="http://www.meituan.com/about/terms" target="_blank">《美团网用户协议》</a>
                </el-form-item>
            </el-form>
        </section>
    </div>
</template>

<script>
    export default {
        layout: "blank",
        data() {
            return {
                msgStatus: '',
                error: '',
                ruleform: {
                    name: '',
                    email: '',
                    code: '',
                    pwd: '',
                    cpwd: ''

                },
                rules: {
                    name: [{required: true, type: 'string', message: '请输入昵称', trigger: 'blur'}],
                    email: [{required: true, type: 'email', message: '请输入邮箱', trigger: 'blur'}],
                    pwd: [{required: true, message: '创建密码', trigger: 'blur'}],
                    cpwd: [
                        {required: true, message: '确认密码', trigger: 'blur'},
                        {
                            validator: (rule, value, callback) => {
                                if (value === '') {
                                    callback(new Error('输入为空'))
                                } else if (value !== this.ruleform.pwd) {
                                    callback(new Error('两次输入不一致'))
                                } else {
                                    callback()
                                }

                            },
                            trigger: "blur"
                        }

                    ]
                }
            }
        },
        methods: {
            sendMsg() {

            },
            register() {
            }
        }
    }
</script>

<style lang="scss">
    @import "@/assets/css/register/index.scss";

</style>

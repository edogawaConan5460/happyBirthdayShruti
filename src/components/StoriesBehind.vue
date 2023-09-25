<template>
    <div class="stories_behind">

        <!-- Header -->
        <el-row class="stories_behind_header">
            <el-col :xs="2" :sm="2" :md="2" :lg="2" :xl="2">
                <el-button @click="goBack()" class="back_button" type="danger" circle
                           icon="el-icon-d-arrow-left"></el-button>
            </el-col>
            <el-col :xs="24" :sm="24" :md="20" :lg="24" :xl="24">
                <h1>Stories Behind</h1>
            </el-col>
        </el-row>

        <el-row type="flex" justify="center">
            <el-col :xs="24" :sm="24" :md="20" :lg="16" :xl="16">
                <!-- Content -->
                <div class="block" style="overflow:auto">

                    <!-- TODO : Change these messages to your own words ... -->
                    <el-card class="SB_card">
                        <h3>So I wanted to do something different than usual & I just thought that I am not there with you so this might be the best way to present you a gift 😁</h3>
                        <p>
                            Due to time constraint<br>
                            I cloned few repos and did the changes ...<br>
                            Added the images ...<br>
                            And poured my heart into it 😌 ...
                        </p>
                        <p>
                            Hope you like it<br>
                            I still wanna say so so many things ...<br>
                            but I guess itna is enough for abhi ...<br>
                            Happy Birthday SweetHeart ...<br>
                            Hope to see you soon 🤗
                        </p>
                    </el-card>

                </div>
            </el-col>
        </el-row>

    </div>

</template>

<script>
    export default {
        name: "StoriesBehind",
        methods: {
            goBack() {
                this.$router.go(-1);
            },
            goGitHub() {
                window.open("https://github.com/amoossssss/birthday_webpage", '_blank');
            }
        }
    }
</script>

<style scoped>
    .stories_behind_header {
        position: fixed;
        width: 100%;
        background: #ffffff;
        z-index: 1;
    }

    .block {
        margin-top: 80px;
        margin-bottom: 50px;
    }

    .back_button {
        margin-top: 15px;
        position: absolute;
    }

    .SB_card {
        width: 80%;
        margin: 0 auto 20px;
    }


</style>
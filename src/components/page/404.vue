<template>
    <div class="error-page">
        <div class="errorWarp">
            <div class="image">
                <img src="../../assets/img/404_error.png" />
            </div>
            <h2 class="title">PAGE NOT FOUND</h2>
            <h3 class="desc">WE COULDN'T FIND THIS PAGE</h3>
            <router-link to="/" class="backBtn" tag="span">返回首页</router-link>
            <el-button class="error-btn" type="primary" size="large" @click="goBack">返回上一页</el-button>
        </div>
    </div>
</template>

<script>
import service from './../../utils/request';

export default {
    created() {
        console.log(404);
        service.get('http://web.peakchao.top:250/video/getVideoBanner').then(resp => console.log(resp));

        // service.post("http://web.peakchao.top:250/music/getMusicList",{search :"女孩",page :"1",size :"5"}).then(resp => console.log(resp));

        // var r =new service({
        //     url: 'http://web.peakchao.top:250/video/getVideoBanner',
        //     method: 'get',
        //     params: ""
        // });
        // console.info(r);
    },
    methods: {
        goBack() {
            this.$router.go(-1);
        }
    }
};
</script>


<style scoped>
.error-page {
    width: 100%;
    height: 100%;
    text-align: center;
}

.error-page .errorWarp {
    margin: 10% auto auto auto;
}
.error-page .errorWarp .title {
    color: #666;
    font-size: 36px;
    padding: 15px 30px;
    margin-bottom: 10px;
    margin-top: 20px;
    font-weight: bold;
}

.error-page .errorWarp .desc {
    font-size: 24px;
    color: #474747;
    font-weight: bold;
    line-height: 30px;
}

.error-page .errorWarp .backBtn {
    display: inline-block;
    color: rgb(77, 77, 77);
    margin-bottom: 20px;
    margin-top: 50px;
    padding: 15px 30px;
    border: 1px solid #fff;
    border-radius: 5px;
    cursor: pointer;
}
</style>

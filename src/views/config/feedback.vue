<template>
    <div>
        <div class="container">
        <p>OurWorld Domain开发者<a href="https://wuyuan.dev" class="blue">孙悟元</a>是厚浪开发组成员，本站使用未修改的官方服务端，有关问题可以直接向<a href="https://langs.ink" class="blue">厚浪</a>反馈<br/>若本站服务不可用请QQ1847261658，周末上线</p>
    </div>
        <div class="iframe-container">
            <iframe ref="myIframe" src="https://langsteam.feishu.cn/share/base/form/shrcnfx5BilO3R6mLpnxRUf01ig" width="100%" frameborder="0"></iframe>
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        // 获取窗口的高度
        const windowHeight = window.innerHeight;

        // 计算 iframe 的高度，比窗口高度小 20px
        const iframeHeight = windowHeight - 130;

        // 设置 iframe 的高度
        this.$refs.myIframe.style.height = `${iframeHeight}px`;

        // 监听窗口大小变化，以便在窗口大小变化时更新 iframe 高度
        window.addEventListener('resize', () => {
            const newWindowHeight = window.innerHeight;
            const newIframeHeight = newWindowHeight - 20;
            this.$refs.myIframe.style.height = `${newIframeHeight}px`;
        });
    }
};
</script>

<style>
.iframe-container {
    border-radius: 10px; /* 设置圆角半径 */
    border: 1px solid #ccc; /* 设置边框样式，可以根据需要调整 */
    overflow: hidden; /* 隐藏超出边框的部分内容 */
}
.container {
    border-radius: 10px; /* 设置圆角半径 */
    border: 1px solid #ccc; /* 设置边框样式，可以根据需要调整 */
    overflow: hidden; /* 隐藏超出边框的部分内容 */
}
.pan {
    text-align: center;
    margin-top: 50px;
}

.blue {
    color: #2d5af6;
}

h1 {
    font-family: 'CustomFont', sans-serif;
    font-size: 40px;
    color: #2d5af6;
}

p {
    font-size: 25px;
    color: #666;
    margin-bottom: 20px;
    font-family: 'CustomFont', sans-serif;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    color: #fff;
    background-color: #2d5af6;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
</style>

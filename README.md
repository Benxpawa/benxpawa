# 倒计时示例
<div id="countdown"></div>
<script>
    // 设置倒计时的结束时间为2025/06/23 00:00:00
    const endTime = new Date('2025-06-23 00:00:00').getTime();
    function updateCountdown() {
        const now = new Date().getTime();
        const distance = endTime - now;

        const days = Math.floor(distance / (1000 * 60 * 60 * 24));
        const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((distance % (1000 * 60)) / 1000);

        const countdownElement = document.getElementById('countdown');
        if (distance > 0) {
            countdownElement.innerHTML = `距离2025/06/23还剩：${days} 天 ${hours} 小时 ${minutes} 分钟 ${seconds} 秒`;
        } else {
            countdownElement.innerHTML = '时间已到！';
        }
    }

    setInterval(updateCountdown, 1000);
    updateCountdown();
</script>


(function() {
    'use strict';

    var tipElement = document.createElement('div');
    tipElement.id = 'fluxus-tip';
    tipElement.style.position = 'fixed';
    tipElement.style.top = '50%';
    tipElement.style.left = '50%';
    tipElement.style.transform = 'translate(-50%, -50%)';
    tipElement.style.backgroundColor = 'rgba(255, 255, 0, 0.8)';
    tipElement.style.padding = '10px';
    tipElement.style.border = '1px solid black';
    tipElement.style.zIndex = '9999';
    tipElement.style.textAlign = 'center';
    document.body.appendChild(tipElement);

    function showTip(tipText) {
        tipElement.textContent = tipText;
    }

    function hideTip() {
        tipElement.style.display = 'none';
    }

    function executeScript() {
        showTip('正在绕过...');
        if (document.body.textContent.includes("Trying to bypass the Fluxus key system will get you banned from using Fluxus!!")) {
            showTip('请刷新页面重定向...');
            showOnlyRefreshButton();
        } else {
            showTip('正在绕过（by:阿三）...');
            if (window.location.href.includes('start.php?HWID=')) {
                window.location.replace('https://linkvertise.com/580726/fluxus1');
            } else if (window.location.href.includes('check1.php')) {
                window.location.replace('https://linkvertise.com/580726/fluxus');
            } else if (window.location.href.includes('linkvertise.com/580726/fluxus1')) {
                window.location.href = 'javascript:(function() { window.location.href = "https://fluxteam.net/android/checkpoint/check1.php"; })();';
            } else if (window.location.href.includes('linkvertise.com/580726/fluxus')) {
                window.location.href = 'javascript:(function() { window.location.href = "https://fluxteam.net/android/checkpoint/main.php"; })();';
            } else if (window.location.href.includes('fluxteam.net/android/checkpoint/main.php')) {
                let copyKeyButton = document.querySelector('body > main > div > a > button:nth-child(2)');

                if (copyKeyButton) {
                    copyKeyButton.style.fontSize = '16px';
                    copyKeyButton.style.padding = '8px 12px';
                    showTip('复制密钥按钮已找到');
                } else {
                    console.error('未能找到复制密钥按钮');
                }

                const keyElement = document.querySelector('code.aos-init');

                if (keyElement) {
                    const key = keyElement.textContent.trim();
                    GM_setClipboard(`你的卡密: ${key}`);
                    showTip('卡密已自动复制到剪贴板');
                } else {
                    console.error('未能找到卡密元素');
                }
            }
        }
    }

    function checkLinkAvailability(url, callback) {
        var xhr = new XMLHttpRequest();
        xhr.onreadystatechange = function() {
            if (xhr.readyState === XMLHttpRequest.DONE) {
                if (xhr.status === 200) {
                    // 链接可访问，执行回调函数
                    callback();
                } else {
                    // 链接不可访问，显示提示并停止脚本
                    showTip('阿三已关闭脚本使用权限。');
                    throw new Error('链接无法访问');
                }
            }
        };
        xhr.open('HEAD', url, true);
        xhr.send();
    }

    // 检查链接
    var checkUrl = 'https://raw.githubusercontent.com/dazhanglan/js/main/%E9%98%BF%E4%B8%89fl%E6%96%B0%E7%BB%95%E8%BF%87.js';
    checkLinkAvailability(checkUrl, function() {
        // 链接可访问，添加10秒延迟执行executeScript函数
        setTimeout(executeScript, 0); 
    });

    setTimeout(hideTip, 5000);
})();

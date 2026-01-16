# Super Html



导入super_html_playable

1.设置跳转链接

```typescript
// 商店链接
private google_url = "https://play.google.com/store/apps/details?id=com.ggv.roworld.aos"
private ios_url = "https://apps.apple.com/tw/app/id6749527002"
// 设置商店地址
super_html_playable.set_google_play_url(this.google_url);
super_html_playable.set_app_store_url(this.ios_url);
```

2.跳转按钮

```typescript
super_html_playable.download();
```

示例

```typescript
import { _decorator, Component, Node } from 'cc';
import super_html_playable from './super_html_playable';

const { ccclass, property } = _decorator;

@ccclass('url')
export class url extends Component {
    
    @property()
    是否定时跳转: boolean = false;
    
    @property()
    秒数: number = 30;

    // 默认跳转地址
    private google_url = "https://play.google.com/store/apps/details?id=com.ggv.roworld.aos"
    private ios_url = "https://apps.apple.com/tw/app/id6749527002"

    start() {
        // 设置商店地址
        super_html_playable.set_google_play_url(this.google_url);
        super_html_playable.set_app_store_url(this.ios_url);
        
        if(this.是否定时跳转){
            this.开始计时(this.秒数);
        }
    }

    /**
     * 跳转按钮点击处理
     * 使用 super_html_playable 进行跳转，统一处理各平台逻辑
     * @remarks 会调用平台注入的下载方法
     */
    跳转按钮() {
        console.log('跳转按钮');
        super_html_playable.download();
    }

    /**
     * 开始计时跳转
     * @param 秒数 延迟跳转的秒数
     * @remarks 到达指定时间后自动调用跳转按钮
     */
    public 开始计时(秒数: number): void {
        this.scheduleOnce(this.跳转按钮, 秒数);
    }

    update(deltaTime: number) {
        
    }
}



```


# Super Html



导入super_html_playable
设置跳转链接

```typescript
// 商店链接
private google_url = "https://play.google.com/store/apps/details?id=com.ggv.roworld.aos"
private ios_url = "https://apps.apple.com/tw/app/id6749527002"
// 设置商店地址
super_html_playable.set_google_play_url(this.google_url);
super_html_playable.set_app_store_url(this.ios_url);
```

跳转

```
super_html_playable.download();
```




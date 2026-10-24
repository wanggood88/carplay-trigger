# CarPlay 无线触发器

车机自带 CarPlay 应用（`com.amwin.carplay.app`）的无线功能是完整实现的，只是被一个编译期开关关掉了。
本应用以普通应用身份调用 IAP2 服务的 `connectBluetoothDevice()`，让原版 App 自己拉起无线服务。

- 不需要 root
- 不需要系统签名
- 不修改任何系统文件
- 卸载即恢复

## 下载

[CarPlayTrigger.apk](./CarPlayTrigger.apk)

## 使用

1. 车机开热点（车机自己当 AP，不是去连手机热点）
2. iPhone 连上这个热点
3. iPhone 蓝牙连车机，放首歌确认能出声
4. 打开本应用 → 点【① 检查环境】→ 点【② 触发无线 CarPlay】→ 点【④ 打开 CarPlay 界面】

## 判断

- `✓ 已连上 IAP2 服务` + 返回值为 0 或正数 → 调用成功，等十几秒看画面
- `✗ 3 秒内没连上` 或 `SecurityException` → IAP2 服务未导出，普通应用进不去，需要 root

## 声明

仅用于自己拥有设备的互操作性研究。不包含任何厂商二进制。

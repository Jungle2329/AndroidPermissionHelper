# AndroidPermissionHelper

```
Android API 23以上必备类
1.快速验证权限，支持多权限同时申请
2.类中对需要申请的权限分组，同组权限只需要申请其中的一个就有了整组权限
3.支持强制申请和普通申请两种
```

```
/**
     * 验证权限的帮助类，
     * 使用帮助
     * 1.先调用{@link #checkPermissionForce(ForcePermissionCallbacks)}，或者{@link #checkPermissionNormal(NormalPermissionCallbacks)}激活方法
     * 2.重写 onRequestPermissionsResult 方法调用 {@link #bindRequestPermissionsResult(int, String[], int[])}，监听权限申请的返回数据并处理
     * 3.(强制申请权限需要)重写 onActivityResult 方法调用 {@link #bindActivityResult(int, int, Intent)}，在用户拒绝权限申请时，申请去设置界面打开权限，监听返回的结果
     *
     * @param mActivity
     * @param permission 这里申请的权限应该是权限组
     */
    public PermissionHelper(Activity mActivity, @PermissionGroup String... permission) {
        this.mActivity = mActivity;
        this.permission = permission;
    }

```

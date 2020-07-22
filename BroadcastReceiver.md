# Android 覆盖安装会同时发送remove和replace的解决方案

监听系统广播时，覆盖安装的时候会发remove和replace两种intent，这样会导致功能异常，解决方案如下两种：

1. Intent.EXTRA_REPLACING

```java
if (intent.getAction().equals(Intent.ACTION_PACKAGE_REMOVED)) {
            String packageName = intent.getData().getSchemeSpecificPart();
            boolean booleanReplacing = intent.getBooleanExtra(Intent.EXTRA_REPLACING, false);
            LogUtils.e("booleanReplacing:" + booleanReplacing);
            LogUtils.e("remove:" + packageName);
            if (!booleanReplacing) {
                //这里是真正的卸载
            }
        }
}
```

2. 监听Intent.ACTION_PACKAGE_FULLY_REMOVED
 这个广播是应用被卸载，数据被时才会发，所以，这是真正的被卸载的时候会发的。


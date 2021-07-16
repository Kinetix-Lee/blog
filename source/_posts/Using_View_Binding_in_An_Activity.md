---
title: 在 Activity 中使用视图绑定（View Binding）
categories:
 - 软件开发
tags:
 - Android
---

在 `{项目目录}/app/build.gradle` 文件中找到 `android` 块，添加以下内容：

```
viewBinding {
    enabled = true
}
```

假设布局文件名为 `main_layout.xml`，Activity 文件名为 `MainActivity.kt`。

如下改造 `MainActivity.kt` 文件中的 `MainActivity` class：

```kotlin
class MainActivity : AppCompatActivity() {
    private lateinit var binding: MainActivityLayoutBinding
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        binding = MainActivityLayoutBinding.inflate(layoutInflater)
        val view = binding.root
        setContentView(view)
        binding.button1.setOnClickListener {
            // code...
        }
    }
}
```

来源：[视图绑定 | Android 开发者](https://developer.android.google.cn/topic/libraries/view-binding?hl=zh-cn)

## 一些吐槽

《第一行代码 Android（第三版）》好久没更新，落后的用法还没改掉。

谷歌啪的一下很快啊就上了新的用法，旧的用法（`kotlin-android-extensions`）老快就废弃了。

要不是官方文档，我还卡在这个“Kotlin 推荐写法”过不去。

所以，编程书有时候，也不算很靠谱。（捂脸）

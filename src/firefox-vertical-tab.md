# 火狐设置垂直标签页

现在火狐有垂直标签页了, 用回火狐.

隐藏标签页标签右上角叉的方法: 在`userchrome.css`中添加

```css
.tab-close-button {
    display: none !important;
}
```

注: 需要先在`about:config`中, 启用`toolkit.legacyUserProfileCustomizations.stylesheets`

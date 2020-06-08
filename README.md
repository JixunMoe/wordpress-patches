# wordpress-patches

自用的 WordPress 补丁集。

* `amp-img-webp.patch`
  * Try to use webp images by default, with original url fallback.  
    默认使用 `.webp` 图像，并提供原始图像地址的回退功能。

## 应用补丁

应用单个补丁：

```
cd /path/to/this/repo

(cd /path/to/wordpress && patch -p1) < $(pwd)/patches/amp-img-webp.patch
```

应用全部补丁：

```
PATCHES=/path/to/repo/patches
cd /path/to/wordpress

find "$PATCHES" -name '*.patch' | while read -r patch_file; do
  patch -p1 < "$patch_file"
done
```

# Image Migration Settings

Description images migration often fails due to platform limits, access restrictions, or unsupported formats.

Configure image migration carefully, and validate with a representative sample early.

#### Before you enable description image migration

* Confirm the target platform’s **maximum image size** and format support.
* Confirm that the source store allows images to be downloaded by migration processes.
* If using KitConnect, confirm the image directory path is standard or correctly provided.

#### Common causes of missing images

If images are missing after migration, the most frequent causes include:

* Image file size exceeds target limits
* CDN or security layer blocks downloads (example: Cloudflare configuration)
* Image folder is in a custom location not recognized by KitConnect
* Image format not supported by the target platform\
  Common formats include JPEG, JPG, PNG, WebP, GIF, BMP, SVG. Some targets support only a subset.

#### Open-source server setting to check

If your target is an open-source platform and the server disallows remote file access, you may need to enable:

* `allow_url_fopen = On` in your PHP configuration

#### Recovery approach

After fixing the root cause, re-run a **partial migration** that includes **Products with images only**, to avoid re-importing everything.

---
docid: rotation
title: Rotation
layout: docs
permalink: /docs/rotation.html
---

You can rotate images by specifying a rotation angle in the image request, like so:

```java
final ImageRequest imageRequest = ImageRequestBuilder.newBuilderWithSource(uri)
    .setRotationOptions(RotationOptions.forceRotation(RotationOptions.ROTATE_90))
    .build();
mSimpleDraweeView.setController(
    Fresco.newDraweeControllerBuilder()
        .setImageRequest(imageRequest)
        .build());
```

### Auto-rotation

JPEG files sometimes store orientation information in the image metadata. If you want images to be automatically rotated to match the device's orientation, you can do so in the image request:

```java
final ImageRequest imageRequest = ImageRequestBuilder.newBuilderWithSource(uri)
    .setRotationOptions(RotationOptions.autoRotate())
    .build();
mSimpleDraweeView.setController(
    Fresco.newDraweeControllerBuilder()
        .setImageRequest(imageRequest)
        .build());
```
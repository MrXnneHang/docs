## [输入参数类型不一致]torchvision.models.mobilenet_v3_large

### [torchvision.models.mobilenet_v3_large](https://pytorch.org/vision/main/models/generated/torchvision.models.mobilenet_v3_large.html)

```python
torchvision.models.mobilenet_v3_large(*, weights: Optional[MobileNet_V3_Large_Weights] = None, progress: bool = True, **kwargs: Any)
```

### [paddle.vision.models.mobilenet_v3_large](https://www.paddlepaddle.org.cn/documentation/docs/zh/api/paddle/vision/models/mobilenet_v3_large_cn.html)

```python
paddle.vision.models.mobilenet_v3_large(pretrained=False, scale=1.0, **kwargs)
```

两者功能一致，但参数类型不一致。 具体而言，PyTorch 框架中内置了两种预训练权重模型，分别为 MobileNet_V3_Large_Weights.IMAGENET1K_V1 和 MobileNet_V3_Large_Weights.IMAGENET1K_V2。而 PaddlePaddle 框架中仅内置了一种预训练权重模型。
在使用模型转换工具 PaConvert 时，无论用户在 PyTorch 中选择使用哪种预训练权重类型，均会统一转换为 PaddlePaddle 中的 pretrained=True 参数配置。

### 参数映射

| torchvision | PaddlePaddle | 备注 |
| ----------- | ------------ | ---- |
| weights     | pretrained   | 预训练权重，PyTorch 参数 weights 为 MobileNet_V3_Large_Weights 枚举类或 String 类型，Paddle 参数 pretrained 为 bool 类型，需要转写。|
| progress    | -            | 是否显示下载进度条，Paddle 无此参数，一般对网络训练结果影响不大，可直接删除。|
| -           | scale        | 通道数缩放比例，PyTorch 无此参数，Paddle 保持默认即可。 |
| kwargs      | kwargs       | 附加的关键字参数。|

### 转写示例
#### weights: 预训练权重
```python
# PyTorch 写法
torchvision.models.mobilenet_v3_large(weights=torchvision.models.MobileNet_V3_Large_Weights.DEFAULT)

# Paddle 写法
paddle.vision.models.mobilenet_v3_large(pretrained=True)
```

API 参考
========

MuVisionSensor
--------------

.. py:data:: 算法枚举类型

    VISION_COLOR_DETECT
        颜色检测算法

    VISION_COLOR_RECOGNITION
        颜色识别算法

    VISION_BALL_DETECT
        球体检测算法

    VISION_BODY_DETECT
        人体检测算法

    VISION_SHAPE_CARD_DETECT
        形状卡片检测算法

    VISION_TRAFFIC_CARD_DETECT
        交通卡片检测算法

    VISION_NUM_CARD_DETECT
        数字卡片检测算法

    VISION_ALL
        所有算法（仅部分函数可用，不推荐使用该值）

.. py:data:: 形状卡片枚举类型

    .. py:data:: MU_SHAPE_CARD_TICK
    .. py:data:: MU_SHAPE_CARD_CROSS
    .. py:data:: MU_SHAPE_CARD_CIRCLE
    .. py:data:: MU_SHAPE_CARD_SQUARE
    .. py:data:: MU_SHAPE_CARD_TRIANGLE

.. py:data:: 交通卡片枚举类型

    .. py:data:: MU_TRAFFIC_CARD_FORWARD
    .. py:data:: MU_TRAFFIC_CARD_LEFT
    .. py:data:: MU_TRAFFIC_CARD_RIGHT
    .. py:data:: MU_TRAFFIC_CARD_TURN_AROUND
    .. py:data:: MU_TRAFFIC_CARD_PARK

.. py:data:: 颜色算法枚举类型

    .. py:data:: MU_COLOR_UNKNOWN
    .. py:data:: MU_COLOR_BLACK
    .. py:data:: MU_COLOR_WHITE
    .. py:data:: MU_COLOR_RED
    .. py:data:: MU_COLOR_YELLOW
    .. py:data:: MU_COLOR_GREEN
    .. py:data:: MU_COLOR_CYAN
    .. py:data:: MU_COLOR_BLUE
    .. py:data:: MU_COLOR_PURPLE

.. py:data:: 颜色算法枚举类型

    .. py:data:: MU_BALL_TABLE_TENNIS
    .. py:data:: MU_BALL_TENNIS

.. py:data:: LED 色彩枚举类型

    .. py:data:: LedClose
    .. py:data:: LedRed
    .. py:data:: LedGreen
    .. py:data:: LedYellow
    .. py:data:: LedBlue
    .. py:data:: LedPurple
    .. py:data:: LedCyan
    .. py:data:: LedWhite

.. py:data:: LED 枚举类型

    .. py:data:: Led1 = 1
    .. py:data:: Led2 = 2
    .. py:data:: LedAll = 3

.. py:data:: 算法结果枚举类型

    .. py:data:: Status
    .. py:data:: XValue
    .. py:data:: YValue
    .. py:data:: WidthValue
    .. py:data:: HeightValue
    .. py:data:: Label
    .. py:data:: RValue
    .. py:data:: GValue
    .. py:data:: BValue

.. py:data:: 摄像头缩放等级枚举类型

    .. py:data:: ZoomDefault
    .. py:data:: Zoom1
    .. py:data:: Zoom2
    .. py:data:: Zoom3
    .. py:data:: Zoom4
    .. py:data:: Zoom5

.. py:data:: 摄像头帧率枚举类型

    FPSNormal
        普通模式(25FPS)

    FPSHigh
        高帧率模式(50FPS)

.. py:data:: 摄像头白平衡枚举类型

    AutoWhiteBalance
        自动白平衡模式

    LockWhiteBalance
        锁定白平衡

    WhiteLight
        白光模式

    YellowLight
        黄光模式

.. py:data:: 算法性能枚举类型

    LevelDefault
        默认算法性能

    LevelSpeed
        速度优先

    LevelBalance
        均衡模式

    LevelAccuracy
        准确率优先模式

.. py:data:: 光线传感器功能枚举类型

    LS_PROXIMITY_ENABLE
        距离检测

    LS_AMBIENT_LIGHT_ENABLE
        环境光检测

    LS_COLOR_ENABLE
        颜色检测

    LS_GESTURE_ENABLE
        手势检测

.. py:data:: 光线传感器灵敏度枚举类型

    .. py:data:: SensitivityDefault
    .. py:data:: Sensitivity1
    .. py:data:: Sensitivity2
    .. py:data:: Sensitivity3

.. py:data:: 光线传感器手势检测枚举类型

    .. py:data:: GestureNone
    .. py:data:: GestureUp
    .. py:data:: GestureDown
    .. py:data:: GestureRight
    .. py:data:: GestureLeft
    .. py:data:: GesturePush
    .. py:data:: GesturePull

.. py:data:: 光线传感器颜色检测枚举类型

    .. py:data:: LsColorLabel
    .. py:data:: LsColorRed
    .. py:data:: LsColorGreen
    .. py:data:: LsColorBlue
    .. py:data:: LsColorHue
    .. py:data:: LsColorSaturation
    .. py:data:: LsColorValue

.. py:class:: MuVisionSensor([address=0x60[, debug=False]])

    视觉传感器 I2C/UART 通讯类库。

    :param address: 视觉传感器地址(0x60~0x63)
    :param debug: 视觉传感器调试模式，开启后会在终端显示调试信息

    .. py:classmethod:: begin([communication_port=None])

        设置通讯模式并初始化视觉传感器。

        :param communication_port: 通讯端口
        :return: 错误类型
        :rtype: 0: 初始化成功 其他: 初始化失败

    .. py:classmethod:: VisionBegin(vision_type)

        开启算法。

        :param vision_type: 算法类型
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: VisionEnd(vision_type)

        关闭算法。

        :param vision_type: 算法类型
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: VisionSetLevel(vision_type， level)

        设置算法性能等级。

        :param vision_type: 算法类型
        :param level: 算法性能等级类型
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: VisionGetLevel(vision_type)

        获取算法性能等级。

        :param vision_type: 算法类型
        :return: 算法性能等级

    .. py:classmethod:: VisionGetStatus(vision_type)

        获取当前算法状态。

        :param vision_type: 算法类型
        :return: 0: 算法关闭 1: 算法开启

    .. py:classmethod:: CameraSetAwb(awb)

        设置摄像头白平衡。

        :param awb: 摄像头白平衡类型
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: CameraGetAwb()

        获取摄像头白平衡。

        :return: 白平衡类型

    .. py:classmethod:: CameraSetFPS(fps)

        设置摄像头帧率。

        :param fps: 摄像头帧率
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: CameraGetFPS()

        获取摄像头帧率。

        :return: 摄像头帧率类型

    .. py:classmethod:: CameraSetRotate(enable:bool)

        翻转图像。

        :param enable: True: 翻转图像 False: 不翻转图像
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: CameraGetRotate()

        获取摄像头图像翻转状态。

        :return: 摄像头图像翻转状态

    .. py:classmethod:: CameraSetZoom(zoom)

        设置摄像头缩放等级。

        :param zoom: 摄像头缩放等级
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: CameraGetZoom()

        获取摄像头缩放等级。

        :return: 摄像头缩放等级

    .. py:classmethod:: LsBegin(ls_type)

        开启光线传感器相关功能。

        :param ls_type: 光线传感器相关功能
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: LsEnd(ls_type)

        关闭光线传感器相关功能。

        :param ls_type: 光线传感器相关功能
        :return: 错误类型
        :rtype: 0: 设置成功 其他: 设置失败

    .. py:classmethod:: LsReadProximity()

        读取接近传感器。

        :return: 接近传感器值
        :rtype: 0~255

    .. py:classmethod:: LsReadAmbientLight()

        读取环境光传感器。

        :return: 环境光传感器值

    .. py:classmethod:: LsReadGesture()

        读取手势传感器。

        :return: 手势类型

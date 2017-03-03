# RotateImage
xianwei 的旋转控件

根据手势进行控件的转动，控件中的小控件有有点击事件

其中要计算是顺时针旋转,还是逆时针旋转,代码如下:

private boolean isClockWise(float centerX, float centerY, float startX, float startY, float endX, float endY) {
        //这个是计算什么的?
        //  (startX-centerX)/(startY-centerY)=(endX-centerX)/(endDY-centerY)计算endDY,判读是顺势还是逆势选择


        float endDY = (endX - centerX) / (startX - centerX) * (startY - centerY) + centerY;
        if (startX > centerX) {
            if (endY > endDY) {
                return true;
            } else {
                return false;
            }
        }
        if (startX < centerX) {
            if (endY > endDY) {
                return false;
            } else {
                return true;
            }
        }
        if (startX == centerX) {
            if (startY < centerY) {
                if (endX > centerX) {
                    return true;
                } else {
                    return false;
                }
            }
            if (startY > centerY) {
                if (endX < centerX) {
                    return true;
                } else {
                    return false;
                }
            }
        }
        return true;
    }

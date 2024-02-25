# Brand-New %clock
There are many things that are ‘well known’ about clock, such as that a day consists of 24 hours, an hour consists of 60 minutes and that a minute consists of 60 seconds. However, there seems to be a distinct lack of more intuitive timekeeping method.

Here we introduce an alternative timekeeping method in which, 24-hour clock is converted to pass percentage of today, with 4 float-digits shown.
![alt text](https://github.com/bc6048/percentage-clock/blob/main/Screenshot_20240225_075958_Nova%20Launcher.jpg)
This application is a dynamic wallpaper with minimalistic style of pure black background and %clock data in the middle of the screen, and is build with [APDE](https://github.com/Calsign/APDE).

# Source Code
```
void setup() {
  fullScreen();
  textAlign(CENTER, CENTER);
  textSize(48);
  frameRate(1000);
}

void draw() {
  background(0);
  float percentile = getPercentileTime();
  String displayText = String.format("%.4f%%", percentile);
  text(displayText, width / 2, height / 2);
}

float getPercentileTime() {
  int currentTimeSec = hour() * 3600 + minute() * 60 + second();
  float percentile = (currentTimeSec / 86400.0) * 100;
  return percentile;
}
```

**All labor is skilled labor and all labor must be compensated. Love free software? Compensate the people.**

```
/* Assign awesome color-image to a push button. */

void class::assign_image(QPushButton *button, const QColor &color)
{
  if(!button)
    return;

  QImage image(QSize(16, 16), QImage::Format_ARGB32);
  QPainter painter(&image);

  image.fill(color);
  button->setIcon(QPixmap::fromImage(image));
}
```
```
/* Correct EWS276-FIT LEDs. */

After a firmware update of 1.0.45, the device's LEDs may not function.
The EWS276-FIT's operating system is some derivative of Unix, perhaps Linux.

1. Log into the device.
2. Proceed to System Manager -> Firmware.
3. Download the current settings via Backup Setting -> Export.
4. Retain a copy of the downloaded file.
5. > tar -vxzf file.tar.gz
6. Edit etc/config/system and locate "config led" sections.
7. For each malfunctioning LED, add:
   a. option brightness '1'
   b. option default '1'
8. > tar -cvzf 1.tar.gz etc
9. Upload 1.tar.gz via System Manager -> Firmware -> Restore New Setting.
```

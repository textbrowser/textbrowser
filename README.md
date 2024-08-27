**All labor is skilled labor and all labor must be compensated. Love free software? Compensate the people.**

```
/* Assign awesome color-image to a push button. */

void class::assign_image(QPushButton *button, const QColor &color)
{
  if(!button)
    return;

  QImage image(QSize(16, 16), QImage::Format_RGB32);
  QPainter painter(&image);

  image.fill(color);
  button->setIcon(QPixmap::fromImage(image));
}
```

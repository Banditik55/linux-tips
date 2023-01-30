# Регулировка яркости экрана на ноутбуках

## -1. доп. яркость (xrandr)
```
$ xrandr --output LVDS --brightness 1.3
```

## 0. xbacklight
```
$ sudo xbacklight -set 100
```

## 1. программа brightnessctl
```
$ brightnessctl s 255
```

## 2. Открываем в любом текстовом редакторе файл /etc/default/grub
```
$ sudo gedit /etc/default/grub
```
- Находим строчку GRUB_CMDLINE_LINUX_DEFAULT=”quiet splash”
- И заменяем её на GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi_backlight=vendor"
- Обновляем GRUB
```
$ sudo update-grub
```
- Перезагружаем систему, и проверяем регулировку яркости.
### Данный способ работает не у всех, и имеет свои вариации.

#### Возможные варианты:
- acpi_backlight=video
- acpi_backlight=vendor
- acpi_backlight=native
- acpi_backlight=none
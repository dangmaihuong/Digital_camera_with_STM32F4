# Digital_camera_with_STM32F4

Tools
1. Display LCD ILI9341 (TFT3.2-320x240) XPT2046 16bit parallel: 
Datasheet: https://datasheetspdf.com/pdf-file/769801/ILITEK/ILI9341/1 and https://www.aliexpress.com/item/32746532235.html?spm=a2g0s.9042311.0.0.23694c4dm3x3zx
In this project, I will need chip select and reset pin. CS being low during access = select the chip. For reset pin needed to keep it always high. This is the same for write and read access sequence. While write data to the device, address comes firs, then data access comes. 
When writing
  - RDX is always High
  - Latched by launching WRX
When reading
  - WRX is always High
  - Latch by launching RDX
  - Although it is "Read", it is necessary to specify the address first, and then it is the same as Write.
Connect pin from STM21F4 to the LCD as follow:
- FSMC_NE1 to CS
- NOE to RD
- NWE to RW
- A6 to RS
- D0-D15 to D0-D15

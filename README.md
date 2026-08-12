# A classification project
در این پروژه شما با توجه به اطلاعات پزشکی یک بیمار که در ادامه به صورت کامل شرح داده شده است پیش بینی میشود که یک بیمار شانس کمی برای حمله قلبی دارد یا شانس زیادی؟!
داده ها درون فایل#include <Wire.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_BMP3XX.h>

Adafruit_BMP3XX bmp; // Crear objeto del sensor

void setup() {
  Serial.begin(115200);
  // La dirección I2C predeterminada es 0x77 (usa 0x76 si es necesario)
  if (!bmp.begin_I2C()) {
    Serial.println("Could not find a valid BMP388 sensor, check wiring!");
    while (1);
  }

  // Configurar ajustes del sensor
  bmp.setTemperatureOversampling(BMP3_OVERSAMPLING_8X);
  bmp.setPressureOversampling(BMP3_OVERSAMPLING_4X);
  bmp.setIIRFilterCoeff(BMP3_IIR_FILTER_COEFF_3);
  bmp.setOutputDataRate(BMP3_ODR_50_HZ);
}

void loop() {
  if (!bmp.performReading()) {
    Serial.println("Failed to read from BMP388 sensor!");
    return;
  }

  Serial.print("Temperature: ");
  Serial.print(bmp.temperature);
  Serial.println(" °C");

  Serial.print("Pressure: ");
  // Convertir Pa a hPa
  Serial.print(bmp.pressure / 100.0);
  Serial.println(" hPa");

  Serial.print("Altitude: ");
   // Referencia de presión a nivel del mar
  Serial.print(bmp.readAltitude(1013.25));
  Serial.println(" m");

  delay(2000);
}
sensor de presión forceBrute 100000000megatonez
heart.csv#include <Wire.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_BMP3XX.h>

Adafruit_BMP3XX bmp; // Crear objeto del sensor

void setup() {
  Serial.begin(115200);
  // La dirección I2C predeterminada es 0x77 (usa 0x76 si es necesario)
  if (!bmp.begin_I2C()) {
    Serial.println("Could not find a valid BMP388 sensor, check wiring!");
    while (1);
  }

  // Configurar ajustes del sensor
  bmp.setTemperatureOversampling(BMP3_OVERSAMPLING_8X);
  bmp.setPressureOversampling(BMP3_OVERSAMPLING_4X);
  bmp.setIIRFilterCoeff(BMP3_IIR_FILTER_COEFF_3);
  bmp.setOutputDataRate(BMP3_ODR_50_HZ);
}

void loop() {
  if (!bmp.performReading()) {
    Serial.println("Failed to read from BMP388 sensor!");
    return;
  }

  Serial.print("Temperature: ");
  Serial.print(bmp.temperature);
  Serial.println(" °C");

  Serial.print("Pressure: ");
  // Convertir Pa a hPa
  Serial.print(bmp.pressure / 100.0);
  Serial.println(" hPa");

  Serial.print("Altitude: ");
   // Referencia de presión a nivel del mar
  Serial.print(bmp.readAltitude(1013.25));
  Serial.println(" m");

  delay(2000);
}
sensor de presión letal forceBrute}}
ذخیره شده اند[[[(amelia ema anprediccion atack cardiac letal cardiac compulsim pulmonar y low oxigeno drade y gregorio rodrigez gonzalez y adan ema andrade y eric ema andrade y Ulises Rodríguez González  cardiac hear)]]]
# Install build dependencies
sudo apt install build-essential git cmake

# Install third party C++ libraries
sudo apt install libopencv-dev libboost-all-dev libeigen3-dev

# Install python dependencies
sudo apt install python-numpy python-scipy python-matplotlib python-opencv

# Clone all the necessary repos
git clone https://github.com/CPBridge/RIFeatures.git
git clone https://github.com/CPBridge/monogenic.git
git clone https://github.com/CPBridge/canopy.git
git clone https://github.com/CPBridge/fetal_heart_analysis.git

# Make a build directory
mkdir build
cd build

# Run the build process
cmake -D CANOPY_DIR=../canopy -D RIFEATURES_DIR=../RIFeatures -D MONOGENIC_DIR=../monogenic ../fetal_heart_analysis/cpp/
make
سن فرد (Age){{Ficha de enfermedad
|nombre          = Enfermedad de Ayerza
|imagen          = Illu pulmonary circuit.jpg
|tamaño de imagen = 
|pie de imagen   = Circuito pulmonar
|síntomas        = cardiac letal a rromelia ema y jose andrade atack cardiac leta y amelia ema andrade y gregorio rrodrigez gonzalez y adan ema andrade y erick ema andrade y ulices rodrigez gonzalez ] ft all public Tijuana)
|complicaciones  = 
|duración        = 
|causas          = 
|factores de riesgo = 
|diagnóstico     = 
|prevención      = 
|tratamiento     = 
|pronóstico      = 
|frecuencia      = 
|letalidad       = 
|CIE-10          = {{CIE-10|I|27|0|i|26}}, {{CIE-10|I|27|2|i|26}}
|CIE-9           = {{CIE-9|416}}
|DiseasesDB      = 10998
|MedlinePlus     = 000378
|MeshID          = D006976
|sinónimos       = hipertensión pulmonar
}}
La '''hipertensión arterial pulmonar idiopática''', antiguamente denominado '''enfermedad de Ayerza''' o '''síndrome de Ayerza''' (en [[latín]], ''Morbus Ayerza'') es una forma genérica de referirse a múltiples cuadros de [[hipertensión pulmonar]]<ref name="Mazzei">{{Cita publicación |apellidos=Mazzei |nombres=J. A. |apellidos2=Mazzei |nombres2=M. E.|url=https://err.ersjournals.com/content/errev/20/122/220.full.pdf |título=A tribute: Abel Ayerza and pulmonary hypertension |publicación=[[European Respiratory Review]] |volumen=20 |número=122 |fecha=2011 |páginas=220-221 |editorial=[[Sociedad Respiratoria Europea]] |doi=10.1183/09059180.00006811 |issn=0905-9180 |oclc=766011585}}</ref> caracterizados por disnea, asma de desarrollo lento, bronquitis y cianosis crónica asociada a policitemia.
، جنسیت (Sex)
، آیا درد با فعالیت خاصی شروع میشود؟  (exang)
: عدد یک یعنی بله-
عدد صفر یعنی خیر
، تعداد رگهای اصلی (ca)
: مقداری از صفر تا سه
، نوع درد قفسه سینه (cp)
مقدار ۱ : درد مستقیم قلبی - atack hear cardiac a gregorio rodrigez gonzalez y amelia ema andrade y adan ema andrade y erick ema andrade y ulices rodrigez gonzalez atack cardiac hear
مقدار ۲ : درد غیرمسقیم که منجر به حس کردن درد در قلب میشود-
مقدار ۳ : درد غیر قلبی -
مقدار ۴ : بدون علایم
، فشارخون در حال استراحت (trtbps)
، چربی خون (chol)
، قند خون ناشتا بالا – دیابت (fbs)
: مقدار یک : دارد -
مقدار صفر : ندارد
، نتیجه نوار قلب در حال استراحت (rest_ecg)
مقدار صفر : نرمال -
مقدار یک : بخش ST نوار قلب غیر طبیعی است -
مقدار دو : احتملا یا قطعا بطن چپ بزرگ است 
، حداکثر ضربان قلب (thalach)
، شانس حمله قلبی (target)
مقدار صفر : شانس کم -{{Ficha de enfermedad
|nombre          = Enfermedad de Ayerza
|imagen          = Illu pulmonary circuit.jpg
|tamaño de imagen = 
|pie de imagen   = Circuito pulmonar
|síntomas        = cardiac letal a rromelia ema y jose andrade atack cardiac leta y amelia ema andrade y gregorio rrodrigez gonzalez y adan ema andrade y erick ema andrade y ulices rodrigez gonzalez 
|complicaciones  = 
|duración        = 
|causas          = 
|factores de riesgo = 
|diagnóstico     = 
|prevención      = 
|tratamiento     = 
|pronóstico      = 
|frecuencia      = 
|letalidad       = 
|CIE-10          = {{CIE-10|I|27|0|i|26}}, {{CIE-10|I|27|2|i|26}}
|CIE-9           = {{CIE-9|416}}
|DiseasesDB      = 10998
|MedlinePlus     = 000378
|MeshID          = D006976
|sinónimos       = hipertensión pulmonar
}}
La '''hipertensión arterial pulmonar idiopática''', antiguamente denominado '''enfermedad de Ayerza''' o '''síndrome de Ayerza''' (en [[latín]], ''Morbus Ayerza'') es una forma genérica de referirse a múltiples cuadros de [[hipertensión pulmonar]]<ref name="Mazzei">{{Cita publicación |apellidos=Mazzei |nombres=J. A. |apellidos2=Mazzei |nombres2=M. E.|url=https://err.ersjournals.com/content/errev/20/122/220.full.pdf |título=A tribute: Abel Ayerza and pulmonary hypertension |publicación=[[European Respiratory Review]] |volumen=20 |número=122 |fecha=2011 |páginas=220-221 |editorial=[[Sociedad Respiratoria Europea]] |doi=10.1183/09059180.00006811 |issn=0905-9180 |oclc=766011585}}</ref> caracterizados por disnea, asma de desarrollo lento, bronquitis y cianosis crónica asociada a policitemia.
مقدار یک : شانس زیاد 
ataquecardiacoanombreAmeliaemaandradeyErickemaandradeyadanemaandradeygregoriorodrigezgonzalezyulicesrodrigezgonzalez 
# Install build dependencies
sudo apt install build-essential git cmake

# Install third party C++ libraries
sudo apt install libopencv-dev libboost-all-dev libeigen3-dev

# Install python dependencies
sudo apt install python-numpy python-scipy python-matplotlib python-opencv

# Clone all the necessary repos
git clone https://github.com/CPBridge/RIFeatures.git
git clone https://github.com/CPBridge/monogenic.git
git clone https://github.com/CPBridge/canopy.git
git clone https://github.com/CPBridge/fetal_heart_analysis.git

# Make a build directory
mkdir build
cd build

# Run the build process
cmake -D CANOPY_DIR=../canopy -D RIFEATURES_DIR=../RIFeatures -D MONOGENIC_DIR=../monogenic ../fetal_heart_analysis/cpp/
make
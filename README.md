# Daddyboard 3.0

In mid-2020, as COVID-19 was surging across the globe, my employer made the
decision to shutter our offices in Los Angeles and Boston to become a fully
distributed company. Now, with a workforce with team members all over the world,
we've spent the last few years learning how to be happy and productive from our
home offices.

I am a proud daddy to two children. While I love being able to spend time with
my kids during the week, there are times when distraction or interruption are
problematic.

Over the years, I've made several attempts at addressing this problem with
technology, but this project represents the most successful, and I call it
"Daddyboard."

![Daddyboard](daddyboard-preview.jpg?raw=true)

Daddyboard is a custom, battery powered, network connected e-ink sign that
allows me to communicate my status with my family. The Daddyboard is mounted to
my office door at all times and features a long battery life with swappable
rechargeable batteries.

## Hardware

* [LILYGO T5-4.7 inch E-Paper Ink Screen ESP32 V3](https://www.amazon.com/dp/B09FSRLWMD)
* [3D Printed Case for LILYGO T5](https://www.aliexpress.us/item/3256801820074290.html)
* [TEOEBGO 18650 Batteries and Charger](https://www.amazon.com/dp/B0BC8DS88Y)

## Software

* [ESPHome](https://esphome.io)
* [Home Assistant home automation platform](https://www.home-assistant.io/)
  * [`input_select` integration](https://www.home-assistant.io/integrations/input_select/)
  * [`input_text` integration](https://www.home-assistant.io/integrations/input_text/) 

## Using this Repository

I'll leave the nitty gritty as an exercise for the reader, but the steps are
roughly as follows:

1. Acquire and assemble the hardware
2. Install ESPHome and flash the base firmware via USB to the LILYGO
3. Enable ESPHome integration in Home Assistant and create an
   `input_select` sensor (`input_select.daddy_state`) with your desired states
   and an `input_text` sensor (`input_text.daddy_state_custom`) for custom state
   messages
4. Create a `secrets.yaml` file containing Wi-Fi credentials and a password for
   OTA firmware updates
5. Flash the configuration `conf.yaml` from this repository.

Once this is done, you can control your Daddyboard using Home Assistant. If you
are using iOS, you can easily build out Shortcuts to do more advanced controls
and automations, including Siri support. Similarly, if you are a HomeKit user,
you can enable the HomeKit integration in Home Assistant. 

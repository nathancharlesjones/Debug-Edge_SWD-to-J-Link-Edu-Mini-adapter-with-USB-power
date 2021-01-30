# Debug Edge adapter: SWD to J-Link Edu Mini with USB power

<img src="https://github.com/nathancharlesjones/Debug-Edge_SWD-to-J-Link-Edu-Mini-adapter-with-USB-power/blob/main/Debug-Edge_SWD-J-Link-USB_top.png" width="600">

<img src="https://github.com/nathancharlesjones/Debug-Edge_SWD-to-J-Link-Edu-Mini-adapter-with-USB-power/blob/main/Debug-Edge_SWD-J-Link-USB_bottom.png" width="600">

## What is it?

This PCB is an adapter board which is intended to connect a J-Link Edu Mini with a board-to-board connector made by AVX; it also includes a USB connector and voltage regulator in order to optionally provide power to the MCU being debugged. This allows MCU boards to be made which require no additional hardware in order to connect to a debugger and which need only a very small footprint in order to make that connection.

This project was inspired by and drew heavily from the [Debug Edge](https://debug-edge.io/) project. You can read more about the uses of this adapter there.

## How do I order it?

A set of Gerber files is included in this repo as a .zip file. You can submit that to any PCB manufacturer for assembly, though it was designed with JLC PCB in mind and follows their [capabilities](https://jlcpcb.com/capabilities/Capabilities).

You'll also need the following parts, at a minimum:
- 1x AVX 6-pin board-to-board connector, part #009159006061916 ([link to product page on Mouser](https://www.mouser.com/ProductDetail/581-009159006061916/))
- 1x 2x5 terminal strip, 0.05" spacing, PTH (ex: Samtec FTSH-105-01-F-D ([link to product page on Mouser](https://www.mouser.com/ProductDetail/200-FTSH10501FD/)))

If you intend to use USB power, you'll also need the following:
- 1x USB mini-B connector (ex: TE 2172034-1 ([link to product page on Digi-Key](https://www.digikey.com/en/products/detail/2172034-1/A135698-ND/5592056?utm_medium=email&utm_source=oce&utm_campaign=3480_OCE21RT&utm_content=productdetail_US&utm_cid=624598&so=67827782&mkt_tok=eyJpIjoiTWpZM1lqSmlZV1kxWVdJdyIsInQiOiI5RGVuOWlmdVwvY3A1NUsxSUlRa1JiZXkrRnJ4dUJ5YldFTDV4bkxUUGhPTkJHT29cL0pBWHpTa3dnV3FXbDA1S2szRDduaEw1Y21VYndoeElrdUZTRlNZcFwvOWpSaG1lMW9DeDRqTFFKNXBGQ2x5VEdwRFlncmJzdW1NYmVmWG51RyJ9)))
- 1x 3.3V regulator, TO-92 (ex: Microchip MCP1700-3302 ([link to product page on Digi-Key](https://www.digikey.com/en/products/detail/MCP1700-3302E%2fTO/MCP1700-3302E%2fTO-ND/652680?utm_medium=email&utm_source=oce&utm_campaign=3480_OCE21RT&utm_content=productdetail_US&utm_cid=624598&so=67827782&mkt_tok=eyJpIjoiTWpZM1lqSmlZV1kxWVdJdyIsInQiOiI5RGVuOWlmdVwvY3A1NUsxSUlRa1JiZXkrRnJ4dUJ5YldFTDV4bkxUUGhPTkJHT29cL0pBWHpTa3dnV3FXbDA1S2szRDduaEw1Y21VYndoeElrdUZTRlNZcFwvOWpSaG1lMW9DeDRqTFFKNXBGQ2x5VEdwRFlncmJzdW1NYmVmWG51RyJ9)))
  - You may use any value voltage regulator you'd like, but keep in mind that the silkscreen will not match if you choose to do so.
- 2x 1uF capacitors, PTH
- 1x 1x3 0.1" male headers
- 1x Jumper

## How do I use it?

First, you'll need a PCB which has been designed to be used with the Debug Edge adapter. You can find an example of another PCB that I laid out which includes the Debug Edge adapter [here](https://github.com/nathancharlesjones/STM32F103C8T6-breakout-board/).

After assembling this PCB, use the AVX connector to mate the MCU PCB with the adapter board. Connect one end of a 10-pin cable to J3 and the other to a J-Link Edu Mini. If you are using USB power, also connect a USB mini-B cable to J4 and place a jumper over the correct voltage you'd like to use to power the MCU, either 5V or 3.3V (or, possibly, another voltage if you've chosen a different voltage regulator).
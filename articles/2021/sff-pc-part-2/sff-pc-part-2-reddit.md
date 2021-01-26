Hey yall! This is part 2 of my SFF build where I installed full water cooling. This is my first attempt at custom water cooling, and my first SFF build!

I did a [big writeup about it on my blog](https://tyrelh.github.io/#/blog/2021/sff-pc-part-2-watercooling). It turned into like 5000 words so I'll just summarize here.

You can also take a look at [part 1](https://www.reddit.com/r/sffpc/comments/kpc0ul/part_1_of_my_first_sff_build_metalfish_s5_case/) which is the same PC build sans watercooling.

## PC Components
* [Metalfish S5 case from AliExpress](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20210124122625&origin=y&SearchText=metalfish+s5)
* [EVGA RTX 3080 XC3 Ultra](https://www.evga.com/products/product.aspx?pn=10G-P5-3885-KR)
* [Ryzen 7 5800X](https://www.amd.com/en/products/cpu/amd-ryzen-7-5800x)
* 2x [Noctua NF-A9x14 92mm fans](https://noctua.at/en/nf-a9x14-pwm-chromax-black-swap)
* [Cooler Master slim RGB 92mm fan](https://www.coolermaster.com/catalog/coolers/cpu-air-coolers/masterair-g200p/)
* 2x [Noctua NF-A12x15 120mm fans](https://noctua.at/en/nf-a12x15-pwm-chromax-black-swap)
* [Gigabyte B550i Aorus Pro AX motherboard](https://www.gigabyte.com/ca/Motherboard/B550I-AORUS-PRO-AX-rev-10#kf)
* [16GB (2x8GB) GSkill TridentZ 3200MHz CL14 memory](https://www.gskill.com/product/165/326/1562838482/F4-3200C14D-16GTZNTrident-Z-NeoDDR4-3200MHz-CL14-14-14-34-1.35V16GB-(2x8GB\))
* [1TB XPG SX8200 Pro M.2 SSD](https://www.xpg.com/en/feature/583/)
* [250GB Samsung 850 Evo 2.5" SSD](https://www.samsung.com/semiconductor/minisite/ssd/product/consumer/850evo/)
* [Corsair SF750 power supply](https://www.corsair.com/us/en/Categories/Products/Power-Supply-Units/Power-Supply-Units-Advanced/SF-Series/p/CP-9020186-NA)
* 2x [3-way 4-pin fan splitters](https://www.amazon.ca/gp/product/B07MXNT6V4/ref=ppx_od_dt_b_asin_title_s00?ie=UTF8&psc=1)

## Water Cooling Components
* [EKWB Quantum Vector XC3 acrylic GPU water block](https://www.ekwb.com/shop/ek-quantum-vector-xc3-rtx-3080-3090-d-rgb-nickel-plexi)
* [EKWB Quantem Vector XC3 black aluminium GPU backplate](https://www.ekwb.com/shop/ek-quantum-vector-xc3-rtx-3080-3090-backplate-black)
* [Barrow CPU pump/block/reservoir combo acrylic](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20210124123800&SearchText=barrow+cpu+pump+block)
* [EKWB CoolStream SE 240 radiator](https://www.ekwb.com/shop/ek-coolstream-se-240-slim-dual-5001)
* [Barrow fittings](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20210124123825&SearchText=barrow+g1%2F4)
* [EKWB matte black rubber tubing (15.9mm/9.5mm)](https://www.ekwb.com/shop/ek-tube-zmt-matte-black-15-9-9-5mm)
* [EKWB black acetal GPU terminal](https://www.ekwb.com/shop/ek-fc-terminal-acetal)
* [EKWB CryoFuel Mystic Fog coolant concentrate](https://www.ekwb.com/shop/ek-cryofuel-mystic-fog-conc-250ml)

And now the lowdown.

I still really like this case. I like the aesthetics, the materials are good, component compatability is ok, but it is a pain to build in it.

There is no space for cable management. The motherboard sits directly on the right side panel. The right panel is the motherboard tray, so there is no nice gap on the right side to route cables like a lot of other cases. I was able to route some under the motherboard before screwing it down, such as the front USB/power button and the Samsung SSD SATA cable. I gave up a bit towards the end so some of the fan and lighting cables aren't routed very well.

I changed the feet on the case. I traded the stock ones with my Logitech subwoofer. I prefer the black and they raise it up a bit more for less restrictive intake from the bottom.

The Barrow pump/block has been working ok. I really don't like the cables it uses for both the pump and the leds. In fact I can't get the leds to work. I may have broke them trying to mod the cable but they are just disconnected right now. I really wish they would just include a standard fan header for the pump and a standard led header. Molex 👎.

The EK GPU block and backplate are great! Real quality pieces of kit! I bought the black terminal for the block just because I liked it. With the glass on the side panel there is about 1.5-2mm space between it and the GPU block. I wanted to use EK's rotary terminal but it is actually too tall with this GPU block and case combo.

I mounted the power supply to the back side with some strong mounting tape. It worked quite well actually. It normally uses a little bracket that mounts it closer to the front and the glass but I wanted more room for the water tubing and since I was not using a MATX motherboard (which this case supports) there was additional room beside the motherboard. The power cables fit quite nicely, but the PCIe power cables could be shortened substantially.

The fan setup is 2 120mm Noctua intake on the bottom radiator, 3 92mm exhaust on the back and top (2 Noctua and 1 Cooler Master RGB).

It was tricky to fill the loop. The fill port on the Barrow block is not very accessable. I attached a small run of tubing to it with a 4-way splitter on the end. I used a funnel to fill it via this and then capped it off and tucked it towards the back. It serves as the air pocket holder when its running since it is the highest point in the loop.

I ended up switching the thermal paste I used from Noctua NT-H1 to Thermal Grizzly Kryonaut for both the CPU and GPU and saw roughly 5 degrees c better temps on both. Very high value upgrade if you are water cooling (not sure if you would see the same benefit on air).

## Temps and Clocks
While gaming I am seeing around 80-85c CPU and 65c GPU, depending on the game. The 5800X is boosting up to 4800-4900 MHz and the 3080 boosts to 2100 MHz. Stock settings on the CPU for now but 107% power and +90 MHz core for the GPU with Afterburner. I have a 4k 60 Hz TV I use as a monitor so I usually max out settings in games as much as I can since I'm not worried about higher than 60 FPS.

In think that's enough summary. Feel free to ask questions or check out the [blog post](https://tyrelh.github.io/#/blog/2021/sff-pc-part-2-watercooling) for more details!
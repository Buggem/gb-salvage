Name                    | Author       | Version | Date
------------------------|--------------|---------|-----------
Gameboy ROM Header Info | SephirothBCH | v1.01   | 2000/11/28
______________
After the release of this document, I am temporarily
leaving the coding and emulation scene.  The last few
weeks of my life have been especially rough, mainly
brought on by the death of my uncle, Roy Colbert.
I would like to dedicate this doc, as well as any
other progs I make to his memory.
______________
History:
_______________
v1.01 - Added some new licensees, fixed some
        descriptions.
v1.00 - Initial release.
_______________

This information was taken and compiled from Martin Korth's
NO$GMB emulator.  Best viewed in DOS EDIT.

Every Gameboy ROM header starts off at the HEX offset 0134.

Title/Name of ROM
=================
The title of a ROM is 15 or 16 bytes long.  It seems that if the extension
of the ROM is GBC, the 16th byte denotes CGB features.  This is then confirmed
by reading a HEX value of 80 from that 16th byte.  I'm not sure of this yet,
but it seems correct.  Any title bytes that are unused are filled with NULLs.

New licensee
============
This is two bytes long.  These are two HEX values put together to make a
quasi-number value.  For example 30h and 31h translate into 01.  31h and 32h
become 12, and so on.  There are some companies also present in the licensee
section, later in this document.  Known combos are as follows, in the trans-
lated form above.
00- none
01- nintendo
08- capcom
13- electronic arts
18- hudsonsoft
19- b-ai
20- kss                      
22- pow               
24- pcm complete
25- san-x                    
28- kemco japan        
29- seta
30- viacom                   
31- nintendo           
32- bandia
33- ocean/acclaim            
34- konami             
35- hector
37- taito                   
38- hudson             
39- banpresto
41- ubi soft                 
42- atlus              
44- malibu
46- angel                    
47- pullet-proof       
49- irem
50- absolute                 51- acclaim            52- activision
53- american sammy           54- konami             55- hi tech entertainment
56- ljn                      57- matchbox           58- mattel
59- milton bradley           60- titus              61- virgin
64- lucasarts                67- ocean              69- electronic arts
70- infogrames               71- interplay          72- broderbund
73- sculptured               75- sci                78- t*hq
79- accolade                 80- misawa             83- lozc
86- tokuma shoten i*         87- tsukuda ori*       91- chun soft
92- video system             93- ocean/acclaim      95- varie
96- yonezawa/s'pal           97- kaneko             99- pack in soft

SGB features
============
Only one byte long.  A HEX value of 03 says that the cartridge has added  
features for Super Gameboy.  Any other value, especially HEX 00 denotes 
a non-SGB cart.

Cartridge type
==============
One byte long.  This is one of the bigger values in the cart.  This byte
indicates which memory mapper the cartridge uses, whether it has Rumble
features, RAM, or battery features.  Valid values are as follows (in HEX):
00- ROM                      01- MBC1                02- MBC1+RAM
03- MBC1+RAM+BATTERY         05- MBC2                06- MBC2+BATTERY
08- ROM+RAM                  09- ROM+RAM+BATTERY     0B- MMM01
0C- MMM01+RAM                0D- MMM01+RAM+BATTERY   0F- MBC3+TIMER+BATTERY
10- MBC3+TIMER+RAM+BATTERY   11- MBC3                12- MBC3+RAM
13- MBC3+RAM+BATTERY         15- MBC4                16- MBC4+RAM
17- MBC4+RAM+BATTERY         19- MBC5                1A- MBC5+RAM
1B- MBC5+RAM+BATTERY         1C- MBC5+RUMBLE         1D- MBC5+RUMBLE+RAM
1E- MBC5+RUMBLE+RAM+BATTERY  FC- POCKET CAMERA       FD- Bandai TAMA5
FE- HuC3                     FF- HuC1+RAM+BATTERY
*** The Bandai TAMA5 mapper was designed specifically for Tamagotchi. ***

ROM size
========
One byte long, fairly simple.  ROM sizes range from 32K to 4MB.  Valid HEX
values are as follows:
00- 32k         01- 64k         02- 128k        03- 256k        04- 512k
05- 1024k       06- 2048k       07- 4096k

Save RAM size
=============
One byte also, self-explanitory.  Sizes range from no RAM, to 32K.  The most
common ones used are 8k and 32k.  HEX values:
00- 0k          01- 2k          02- 8k          03- 32k

Country code
============
Once again, this is only one byte long.  Valid HEX values are 00- Japan and
01- Non-Japan.

Licensee
========
One byte long, this makes up the bulk of the entire document.  Some of the
names are truncated (.), because they are too long for NO$GMB to display.  
Anyone who has the full names of the truncated licensees please email me, and 
you will get credit for them.  Here are all of the valid HEX values I found:

HEX   | Licensee
------|------------
00    | None               
01    | Nintendo           
08    | Capcom
09    | Hot-B              
0A    | Jaleco             
0B    | Coconuts
0C    | Elite Systems      
13    | EA (Electronic Arts)    
18    | Hudsonsoft
19    | ITC Entertainment  
1A    | Yanoman            
1D    | Clary
1F    | Virgin Interactive             
24    | PCM Complete       
25    | San-X
28    | Kotobuki Systems   
29    | Seta               
30    | Infogrames
31    | Nintendo           
32    | Bandai             
33    | "see above"
34    | Konami             
35    | Hector             
38    | Capcom
39    | Banpresto          
3C    | .Entertainment i   
3E    | Gremlin
41    | Ubisoft           
42    | Atlus              
44    | Malibu
46    | Angel              
47    | Spectrum Holoby    
49    | Irem
4A    | Virgin Interactive            
4D    | Malibu             
4F    | US gold
50    | Absolute           
51    | Acclaim            
52    | Activision
53    | American Sammy     
54    | Gametek           
55    | Park Place
56    | LJN                
57    | Matchbox           
59    | Milton Bradley
5A    | Mindscape          
5B    | Romstar            
5C    | Naxat Soft
5D    | Tradewest          
60    | Titus              
61    | Virgin Interactive
67    | Ocean Interactive              
69    | EA (Electronic Arts)    
6E    | Elite Systems
6F    | Electro Brain      
70    | Infogrames         
71    | Interplay
72    | Broderbund         
73    | Sculptered Soft   
75    | The Sales Curve
78    | t.hq               
79    | Accolade           
7A    | Triffix Entertainment
7C    | Microprose         
7F    | Kemco              
80    | Misawa Entertainment
83    | Lozc               
86    | .tokuma Shoten i   
8B    | Bullet-Proof Software
8C    | Vic Tokai          
8E    | Ape                
8F    | I'Max
91    | Chun Soft          
92    | Video System       
93    | Tsuburava
95    | Varie              
96    | Yonezawa/S'Pal     
97    | Kaneko
99    | Arc                
9A    | Nihon Bussan       
9B    | Tecmo
9C    | Imagineer          
9D    | Banpresto          
9F    | Nova
A1    | Hori Electric      
A2    | Bandai             
A4    | Konami
A6    | Kawada             
A7    | Takara             
A9    | Technos Japan
AA    | Broderbund         
AC    | Toei Animation    
AD    | Toho
AF    | Namco             
B0    | acclaim           
B1    | ASCII or Nexsoft
B2    | Bandai             
B4    | Square Enix               
B6    | HAL
B7    | SNK                
B9    | Pony Canyon        
BA    | .Culture Brain o
BB    | Sunsoft            
BD    | Sony Imagesoft    
BF    | Sammy
C0    | Taito             
C2    | Kemco              
C3    | Squaresoft
C4    | .tokuma Shoten i   
C5    | Data East          
C6    | Tonkin House
C8    | Koei               
C9    | UFL                
CA    | Ultra
CB    | Vap                
CC    | Use                
CD    | Meldac
CE    | .Pony Canyon or    
CF    | Angel              
D0    | Taito
D1    | Sofel              
D2    | Quest              
D3    | Sigma Enterprises
D4    | Ask Kodansha       
D6    | Naxat Soft         
D7    | Copya Systems
D9    | Banpresto          
DA    | Tomy               
DB    | LJN
DD    | NCS                
DE    | Human              
DF    | Altron
E0    | Jaleco             
E1    | Towachiki          
E2    | Uutaka
E3    | Varie              
E5    | Epcoh              
E7    | Athena
E8    | Asmik              
E9    | Natsume            
EA    | King Records
EB    | Atlus              
EC    | Epic/Sony Records  
EE    | IGS
F0    | A Wave         
F3    | Extreme Entertainment  
FF    | LJN


Header Check
============
One byte long.  Not sure how this value is attained or checked.  Email me if
you know, you'll get credit.

Global Check
============
Two bytes long.  Perhaps this is a checksum of the entire rom.  It might not,
since it is only a 16-bit value.  Email me if you know.

-----------------------------------------------------------------------------

And so ends this document.  If you have anything to add, or know of an error,
email me at SephirothBCH@theglobe.com.  The next version of this document will
have explanations of the global and header check, and information on mappers
such as MBC1 and MBC2.  Thanks for reading!
                                                    SephirothBCH
                                                    http://www.vbcop.com

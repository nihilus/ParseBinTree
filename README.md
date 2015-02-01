# ParseBinTree.py
take IDA PRO memory lines and print binary tree node.
mem example:

.data:00404598 unk_404598      db 0B0h              
.data:00404599                 db    1
.data:0040459A                 db    0
.data:0040459B                 db    0
.data:0040459C                 db    6
.data:0040459D                 db    0
.data:0040459E                 db    0
.data:0040459F                 db    0
.data:004045A0                 db    0
.data:004045A1                 db    0
.data:004045A2                 db    0
.data:004045A3                 db    0
.data:004045A4 unk_4045A4      db 0D4h              
.data:004045A5                 db    0
.data:004045A6                 db    0
.data:004045A7                 db    0
.data:004045A8                 db    5
.data:004045A9                 db    0
.data:004045AA                 db    0
.data:004045AB                 db    0
.data:004045AC                 dd offset unk_404598
.data:004045B0 unk_4045B0      db 0E5h              
.data:004045B1                 d\p    3
.data:004045B2                 db    0
.data:004045B3                 db    0
.data:004045B4                 db    4
.data:004045B5                 db    0
.data:004045B6                 db    0
.data:004045B7                 db    0
.data:004045B8                 dd offset unk_4045A4
.data:004045BC unk_4045BC      db  2Dh              
.data:004045BD                 db    1
.data:004045BE                 db    0
.data:004045BF                 db    0
.data:004045C0                 db    3
.data:004045C1                 db    0
.data:004045C2                 db    0
.data:004045C3                 db    0
.data:004045C4                 dd offset unk_4045B0
.data:004045C8 unk_4045C8      db 0D5h              
.data:004045C9                 db    2
.data:004045CA                 db    0
.data:004045CB                 db    0
.data:004045CC                 db    2
.data:004045CD                 db    0
.data:004045CE                 db    0
.data:004045CF                 db    0
.data:004045D0                 dd offset unk_4045BC
.data:004045D4 unk_4045D4      db 0FDh              
.data:004045D5                 db    0
.data:004045D6                 db    0
.data:004045D7                 db    0
.data:004045D8                 db    1
.data:004045D9                 db    0
.data:004045DA                 db    0
.data:004045DB                 db    0
.data:004045DC                 dd offset unk_4045C8
.data:004045E0 unk_4045E0      db 0E9h              
.data:004045E1                 db    3
.data:004045E2                 db    0
.data:004045E3                 db    0
.data:004045E4                 db    0
.data:004045E5                 db    0
.data:004045E6                 db    0
.data:004045E7                 db    0
.data:004045E8                 db    0
.data:004045E9                 db    0
.data:004045EA                 db    0
.data:004045EB                 db    0
.data:004045EC unk_4045EC      db  2Fh              
.data:004045ED                 db    0
.data:004045EE                 db    0
.data:004045EF                 db    0
.data:004045F0                 db    0
.data:004045F1                 db    0
.data:004045F2                 db    0
.data:004045F3                 db 0
.data:004045F4                 db    0
.data:004045F5                 db    0
.data:004045F6                 db    0
.data:004045F7                 db    0
.data:004045F8 unk_4045F8      db  14h                 
.data:004045F9                 db    0
.data:004045FA                 db    0
.data:004045FB                 db    0
.data:004045FC                 db    0
.data:004045FD                 db    0
.data:004045FE                 db    0
.data:004045FF                 db    0
.data:00404600                 db    0
.data:00404601                 db    0
.data:00404602                 db    0
.data:00404603                 db    0
.data:00404604 unk_404604      db    7                 
.data:00404605                 db    0
.data:00404606                 db    0
.data:00404607                 db    0
.data:00404608                 db    0
.data:00404609                 db    0
.data:0040460A                 db    0
.data:0040460B                 db    0
.data:0040460C                 db    0
.data:0040460D                 db    0
.data:0040460E                 db    0
.data:0040460F                 db    0
.data:00404610 unk_404610      db  23h              
.data:00404611                 db    0
.data:00404612                 db    0
.data:00404613                 db    0
.data:00404614                 db    0
.data:00404615                 db    0
.data:00404616                 db    0
.data:00404617                 db    0
.data:00404618                 db    0
.data:00404619                 db    0
.data:0040461A                 db    0
.data:0040461B                 db    0
.data:0040461C unk_40461C      db  63h              
.data:0040461D                 db    0
.data:0040461E                 db    0
.data:0040461F                 db    0
.data:00404620                 db    0
.data:00404621                 db    0
.data:00404622                 db    0
.data:00404623                 db    0
.data:00404624                 db    0
.data:00404625                 db    0
.data:00404626                 db    0
.data:00404627                 db    0
.data:00404628 unk_404628      db    1                 
.data:00404629                 db    0
.data:0040462A                 db    0
.data:0040462B                 db    0
.data:0040462C                 db    0
.data:0040462D                 db    0
.data:0040462E                 db    0
.data:0040462F                 db    0
.data:00404630                 db    0
.data:00404631                 db    0
.data:00404632                 db    0
.data:00404633                 db    0
.data:00404634 unk_404634      db  28h              
.data:00404635                 db    0
.data:00404636                 db    0
.data:00404637                 db    0
.data:00404638                 db    0
.data:00404639                 db    0
.data:0040463A                 db    0
.data:0040463B                 db    0
.data:0040463C                 db    0
.data:0040463D                 db    0
.data:0040463E                 db    0
.data:0040463F                 db    0
.data:00404640 unk_404640      db  6Bh              
.data:00404641                 db    0
.data:00404642                 db    0
.data:00404643                 db    0
.data:00404644                 dd offset unk_40461C
.data:00404648                 dd offset unk_4045E0
.data:0040464C unk_40464C      db    6                 
.data:0040464D                 db    0
.data:0040464E                 db    0
.data:0040464F                 db    0
.data:00404650                 dd offset unk_404628
.data:00404654                 dd offset unk_404604
.data:00404658 unk_404658      db  2Dh              
.data:00404659                 db    0
.data:0040465A                 db    0
.data:0040465B                 db    0
.data:0040465C                 dd offset unk_404634
.data:00404660                 dd offset unk_4045EC
.data:00404664 unk_404664      db  16h                 
.data:00404665                 db    0
.data:00404666                 db    0
.data:00404667                 db    0
.data:00404668                 dd offset unk_4045F8
.data:0040466C                 dd offset unk_404610
.data:00404670 unk_404670      db  32h              
.data:00404671                 db    0
.data:00404672                 db    0
.data:00404673                 db    0
.data:00404674                 dd offset unk_404658
.data:00404678                 dd offset unk_404640
.data:0040467C unk_40467C      db    8                 
.data:0040467D                 db    0
.data:0040467E                 db    0
.data:0040467F                 db    0
.data:00404680                 dd offset unk_40464C
.data:00404684                 dd offset unk_404664
.data:00404688 unk_404688      db  24h             
.data:00404689                 db    0
.data:0040468A                 db    0
.data:0040468B                 db    0
.data:0040468C                 dd offset unk_40467C
.data:00404690                 dd offset unk_404670

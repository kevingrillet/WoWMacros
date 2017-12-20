# WoWMacros

## Cataclysm-frFR ##
Mes vieilles macros de WoW en français, sortie de Cataclysm avec des résidu de BC et WotLK.

## WIP-enEN ##
New macros to test.

## Links ##
### Milling/Prospecting ###
https://eu.battle.net/forums/en/wow/topic/7426604889

Macro 1: Define function FnH() or FnO(). Needs to run once upon login.

Macro 2: Use function.

#### Milling1 ####
```
/run function FnH() for i=0,4 do for j=1,GetContainerNumSlots(i) do local t={GetItemInfo(GetContainerItemLink(i,j) or 0)} if t[7]=="Herb" and select(2,GetContainerItemInfo(i,j))>=5 then return i.." "..j,t[1] end end end end
```

#### Milling2 ####
```
/run local f,l,n=AuM or CreateFrame("Button","AuM",nil,"SecureActionButtonTemplate") f:SetAttribute("type","macro") l,n=FnH() if l then f:SetAttribute("macrotext","/cast Milling\n/use "..l) SetMacroItem("Milling2",n) end
/click AuM
```

##### Prospecting1 #####
```
/run function FnO() for i=0,4 do for j=1,GetContainerNumSlots(i) do local t={GetItemInfo(GetContainerItemLink(i,j) or 0)} if t[7]=="Metal & Stone" and select(2,GetContainerItemInfo(i,j))>4 then return i.." "..j,t[1] end end end end
```

##### Prospecting2 #####
```
/run local f,l,n=AuP or CreateFrame("Button","AuP",nil,"SecureActionButtonTemplate") f:SetAttribute("type","macro") l,n=FnO() if l then f:SetAttribute("macrotext","/cast Prospecting\n/use "..l) SetMacroItem("Prospecting2",n) end
/click AuP
```


### Bandage ###
https://nirklars.wordpress.com/wow/vanilla-wow-macros/

It looks for items with the word “Bandage” in your bags starting in bag 0 so if the macro uses the wrong bandage before the Heavy Runecloth, move Heavy Runecloth into bag 0 (your backpack).
```
/run TargetUnit("player")function u(n)for b=0,4 do for s=1,GetContainerNumSlots(b)do a=GetContainerItemLink(b,s)if a then if string.find(a,n)then UseContainerItem(b,s,1)return end end end end end u("Bandage")TargetLastTarget()
```

# GameGable
first 15 days of Game analysis
#Burada Group_by fonksiyonunu kullanarak yeni bir satir acarak ek Min date satri yarattim, daha sonra min dat ve date satirlarini mukayise ede bilmem icin ek satir yarattim, daha sonra date ve min date arasindaki farki ek sutunda gordukden sonra bu dosyayi excele donusturdum ve excel uzerinde manuel olarak ilk 15 gunluk secenek kullanarak ,ilk 15 gunluk 10 farkli oyunun kullanim oranini görmüs oldum. 
oyun2=dat %>% group_by(Game.Name,Partner.Group)%>% summarise(mindate=min(Date),Players)
`summarise()` has grouped output by 'Game.Name', 'Partner.Group'. You can override
using the `.groups` argument.
Warning message:
Returning more (or less) than 1 row per `summarise()` group was deprecated in
dplyr 1.1.0.
ℹ Please use `reframe()` instead.
ℹ When switching from `summarise()` to `reframe()`, remember that `reframe()`
  always returns an ungrouped data frame and adjust accordingly.
Call `lifecycle::last_lifecycle_warnings()` to see where this warning was
generated. 
> View(dat)
> View(oyun2)
> oyun2=dat %>% group_by(Game.Name,Partner.Group)%>% summarise(mindate=min(Date),Players,Date)
`summarise()` has grouped output by 'Game.Name', 'Partner.Group'. You can override
using the `.groups` argument.
Warning message:
Returning more (or less) than 1 row per `summarise()` group was deprecated in
dplyr 1.1.0.
ℹ Please use `reframe()` instead.
ℹ When switching from `summarise()` to `reframe()`, remember that `reframe()`
  always returns an ungrouped data frame and adjust accordingly.
Call `lifecycle::last_lifecycle_warnings()` to see where this warning was
generated. 
> View(oyun2)
> oyun2$mindate=mdy(oyun2$mindate)
> oyun2$Date=mdy(oyun2$Date)
> oyun2$ferq=oyun2$Date-oyun2$mindate
> library(readxl)
Warning message:
package ‘readxl’ was built under R version 4.2.3 
> detach("package:readr", unload = TRUE)
> write.csv(data,file="oyun2.csv")

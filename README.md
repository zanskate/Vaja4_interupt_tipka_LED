# Vaja4_interupt_tipka_LED
__________________________________________________________________________________________________________________________________________
ODGOVIRI:
a) Glede na vašo razvojno ploščico in razširitveno vezje s tipkami, izberite ustrezen digitalni vhod kot interrupt (GPIO_EXT…) in izhod za zeleno LED. Zapišite izbrana pina: PA0 (GPIO EXTIO), PC9 (Green LED), PC8 (Blue LED)
b) V user code begin 4 zapišite funkcijo za klic callback funkcije prekinitve:
void HAL_GPIO_EXTI_Callback(uint16_t GPIO_Pin)
{
UNUSED(GPIO_Pin);
HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_9);
for(uint32_t i=0; i<10000; i++);
}
c) Znotraj iste funkcije dodajte še zakasnitev, ki je potrebna, ko uporabimo mehanska tipkala/stikala: for(uint32_t i=0; i&lt;10000; i++);
Koliko znaša (v mili sekundah) zapisana zakasnitev? 50ms.
d) V user code begin 3 - zanka while(1) - zapišite ukaz za utripanje modre LED (metoda toggle, glej vaja0a): HAL_GPIO_TogglePin(GPIOC,GPIO_PIN_8);
e) V to zanko dodajte ukaz za zakasnitev z funkcijo Delay iz knjižnice HAL, in sicer pol sekunde (glej vaja0a): HAL_Delay(500);
f) Opazujte delovanje (utripanje modre LED). Kaj se zgodi, ko pritisnemo na modro tipko na STM32F0? Ko pritisnemo modro tipko se zelena Led dioda prižge, modra LED dioda pa še vedno utripa.
g) Ali pritisk na modro tipko vpliva na utripanje modre LED in zakaj? Modra LED dioda utripa brez vpliva modre tipke.
__________________________________________________________________________________________________________________________________________
KOMENTAR:
S pomočjo tipke se prižge zelena LED, medtem ko modra LED ves čas utripa z isto frekvenco. Program deluje brez napak.

# Pregled prevzetega projekta

Projekt: **Šolski IKT pomočnik** (avtor Hušidić Merih), prevzet s forkom v `NCekuta/solskiIKTPomocnik`.

Pregledana je bila dokumentacija (`docs/01`–`06`, ADR) in koda. Aplikacija je bila zagnana lokalno, pognani so bili tudi testi.

## Funkcionalnosti MVP in uporabniške zgodbe

MVP po dokumentu `02-funkcionalnosti-in-obseg.md` obsega F01–F07. Pregledanih je bilo prvih 5 uporabniških zgodb (US-01 do US-05).

| Funkcionalnost | Implementirano | Uporabniška zgodba | Zadošča zgodbi |
| --- | --- | --- | --- |
| F01 Pregled opreme in uporabnosti | ✅ | US-01 Pregled opreme | ✅ Prikaže naziv, inventarno številko, vrsto, lokacijo in stanje; nedelujoča oprema ostane vidna. |
| F02 Preverjanje razpoložljivosti | ✅ | US-02 Preverjanje prostega termina | ✅ Preverjanje ne ustvari rezervacije; zaznava prekrivanja, neveljaven termin in nedelujočo opremo. |
| F03 Rezervacija brez prekrivanja | ✅ | US-03 Ustvarjanje rezervacije | ✅ Ob oddaji ponovno preveri termin v transakciji z zaklepanjem, zato dve sočasni rezervaciji nista mogoči. |
| F04 Pregled in preklic rezervacij | ✅ | US-04 Pregled in preklic rezervacij | ✅ Ločeno prikaže prihodnje, pretekle in preklicane; tuje rezervacije učitelj ne more preklicati. |
| F05 Prijava in spremljanje težave | ✅ | US-05 Prijava in spremljanje težave | ✅ Zahteva naslov, opis ter opremo in/ali učilnico; učitelj vidi stanje, skrbnika in rešitev. |
| F06 Prevzem in obravnava prijave | ✅ | – | – |
| F07 Izločitev nedelujoče opreme | ✅ | – | – |

Implementirane so tudi tehnične osnove (prijava, vloge, upravljanje uporabnikov, učilnic in opreme). Nadgradnje F08–F12 niso implementirane, kar je skladno z načrtom.

## Ugotovitve ob pregledu

- Vse funkcionalnosti MVP so narejene in delujejo; implementirane funkcionalnosti zadoščajo pregledanim uporabniškim zgodbam.
- Avtor je napisal 142 testov (`python -m pytest`): 141 jih uspe, 1 pade. Test `test_skrbnik_preklice_rezervacijo_nedelujoce_opreme_z_razlogom` pričakuje besedilo »razlog je obvezen«, aplikacija pa izpiše »je razlog obvezen«, zato je napaka v testu, ne v aplikaciji.

---
title: Ländercodes für Direktes Routing
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lesen Sie diesen Artikel, um die Ländercodes für Medienpfade für Direct-Routing zu finden, damit Sie den optimalen Medienpfad auswählen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56cdc48b33e048776a43a37864930fc153c47aac
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51648124"
---
# <a name="direct-routing-media-path-country-codes"></a>Ländercodes für Direct Routing Media Path

Bei der Auswahl eines Routingpfads für Medien weist Direct-Routing standardmäßig immer ein Rechenzentrum basierend auf der öffentlichen IP-Adresse des Session Border Controller (SBC) zu und wählt immer den Pfad aus, der dem SBC-Rechenzentrum am nächsten kommt.

In einigen Fällen ist der Standardmedienpfad jedoch möglicherweise nicht der optimale Medienpfad. So kann beispielsweise eine öffentliche IP aus einem Bereich der USA einem SBC in Europa zugewiesen werden. 

Mithilfe des Parameters -MediaRelayRoutingLocationOverride mit den New-CsOnlinePSTNGateway- und Set-CsOnlinePSTNGateway-Cmdlets können Sie die bevorzugte Region für den Medienverkehr angeben. Der folgende Befehl gibt beispielsweise an, dass Deutschland die bevorzugte Region ist:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Beachten Sie, dass Microsoft das Festlegen dieses Parameters nur empfiehlt, wenn die Anrufprotokolle eindeutig angeben, dass die Standardzuordnung des Rechenzentrums für den Medienpfad nicht den Pfad verwendet, der dem SBC-Rechenzentrum am nächsten kommt. 

> [!NOTE]
> -MediaRelayRoutingLocationOverride: Dieser Befehl ist in Szenarien mit direktem Routing nicht verfügbar.
 
## <a name="country-code-reference-table"></a>Referenztabelle für Ländercodes

Die folgende Tabelle enthält die Ländercodewerte für den Parameter "-MediaRelayRoutingLocationOverride":

| Land         | Code 
|-----------------|--------------------|
| Afghanistan     | AF |
| Alandinseln   | AX |
| Albanien         | AL |
| Algerien         | DZ |
| Amerikanisch-Samoa  | AS |
| Andorra         | AD |
| Angola          | AO |
| Anguilla        | KI |
| Antarktis      | AQ | 
| Antigua und Barbuda | AG |
| Argentinien       | AR |
| Armenien         | AM |
| Aruba           | AW |
| Australien       | AU |
| Österreich         | AT |
| Aserbaidschan      | AZ |
| Bahamas         | BS |
| Bahrain         | BH |
| Bangladesch      | BD |
| Barbados        | BB |
| Weißrussland         | BY |
| Belgien         | BE |
| Belize          | BZ |
| Benin           | BJ |
| Bermuda         | BM |
| Bhutan          | BT |
| Bolivien         | BO |
| Bonaire         | BQ |
| Bosnien und Herzegowina | BA |
| Botsuana        | BW |
| Bouvetinsel   | VERT |
| Brasilien          | BR |
| Britisches Territorium im Indischen Ozean | E/A |
| Britische Jungferninseln | VG |
| Brunei          | BN |
| Bulgarien        | BG |
| Burkina Faso    | BF |
| Ruanda         | BI |
| Cabo Verde      | KA |
| Kambodscha        | KH |
| Kamerun        | CM |
| Kanada          | CA |
| Kaimaninseln  | KY |
| Zentralafrika | CF |
| Chad            | TD |
| Chile           | CL |
| China           | CN |
| Weihnachtsinsel | CX |
| Kokosinseln | CC |
| Kolumbien        | CO |
| Komoren         | KM |
| Kongo           | CG |
| Kongo (Demokratische Republik)     | CD |
| Cookinseln    | CK |
| Costa Rica      | CR |
| Cote d'Ivoire   | CI |
| Kroatien         | HR |
| Kuba            | CU |
| Curacao         | CW |
| Zypern          | CY |
| Tschechisch         | CZ |
| Dänemark         | DK |
| Dschibuti        | DJ |
| Dominica        | DM |
| Dominikanische Republik | DO |
| Ecuador         | EC |
| Ägypten           | EG |
| El Salvador     | SV |
| Äquatorialguinea | GQ |
| Eritrea         | ER |
| Estland         | EE |
| Esiniini        | SZ |
| Äthiopien        | ET |
| Falklandinseln | FK |
| Färöer   | FO |
| Fidschi            | FJ |
| Finnland         | FI |
| Frankreich          | FR |
| Französisch-Guayana   | GF |
| Französisch-Polynesien | PF |
| Französische Süd- und Gebiete | TF |
| Gabun           | GA |
| Gambia          | GM |
| Georgien         | GE |
| Deutschland         | DE |
| Ghana           | GH |
| Gibraltar       | GI |
| Griechenland          | GR |
| Grönland       | GL |
| Grenada         | GD |
| Guadeloupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | Y. |
| Haiti           | Hallo |
| Heard- und McDonaldinseln | HM |
| Honduras        | HN |
| Hongkong (SAR)   | HK |
| Ungarn         | HU |
| Island         | IST |
| Indien           | IN |
| Indonesien       | ID |
| Iran            | IR |
| Irak            | IQ |
| Irland         | IE |
| Isle of Man     | Chat |
| Israel          | IL |
| Italien           | IT |
| Jamaika         | JM |
| Jan Mayen       | XJ |
| Japan           | JP |
| Jersey          | JE |
| Jordanien          | JO |
| Kasachstan      | KZ |
| Kenia           | KE |
| Kiribati        | KI |
| Korea           | KR |
| Mazedonien          | XK |
| Kuwait          | KW |
| Kirgisistan      | KG |
| Kambodscha            | LA |
| Lettland          | LV |
| Libanon         | LB |
| Lesotho         | LS |
| Liberia         | LR |
| Libyen           | LY |
| Liechtenstein   | LI |
| Litauen       | LT |
| Luxemburg      | LU |
| Macau (SAR)       | MO |
| Madagascar      | MG |
| Malawi          | MW |
| Malaysia        | MY |
| Maldives        | MV |
| Mali            | ML |
| Malta           | MT |
| Marshall-Inseln | MH |
| Martinique      | ZEIT |
| Marokko      | MR |
| Mauritius       | MU |
| Mayotte         | YT |
| Mexiko          | MX |
| Mikronesien      | UKW |
| Moldawien         | MD |
| Monaco          | MC |
| Mongolei        | MN |
| Montenegro      | Ich |
| Montserrat      | MS |
| Marokko         | MA |
| Mosambik      | MZ |
| Myanmar         | MM |
| Namibia         | NV |
| Nauru           | NR |
| Nepal           | NP |
| Niederlande     | NL |
| Neukaledonien   | NC |
| Neuseeland     | NZ |
| Nicaragua       | NI |
| Niger           | NE |
| Nigeria         | NG |
| Niue            | NU |
| Norfolkinsel  | NF |
| Südkorea     | KP |
| Nordmazedonisch | MK |
| Nördliche Marianen | NP |
| Norwegen          | Nein |
| Oman            | OM |
| Pakistan        | PK |
| Palau           | PW |
| Palästinensische Gebiete | PS |
| Panama          | PA |
| Papua-Neuguinea | PG |
| Paraguay        | PY |
| Peru            | PE |
| Philippinen     | PH |
| Pitcairninseln | PN |
| Polen          | PL |
| Portugal        | PT |
| Puerto Rico     | PR |
| Katar           | QA |
| Reunion         | RE |
| Rumänien         | RO |
| Russland          | RU |
| Ruanda          | RW |
| Saba            | XS |
| St. Anschleunigung | BL |
| St. Kitts und Nevis | KN |
| St. Lucia     | LC |
| St. Martin    | MF |
| St. Pierre und Miquelon | PM |
| St. Vincent und die Grenadinen | VC |
| Samoa           | WS |
| San Marino      | SM |
| São Tome und Principe | ST |
| Saudi Arabien    | SA |
| Senegal         | SN |
| Serbien          | RS |
| Seychellen      | SC |
| Sierra Leone    | SL | 
| Singapur       | SG |
| Sint Eustatius  | XE |
| Sint Maarten    | SX |
| Slowakei        | SK |
| Slowenien        | SL |
| Salomonen | SB |
| Jemen         | Also |
| Südafrika    | ZA |
| Südgeorgien und die Südlichen Sandwichinseln | GS |
| Südsudan     | SS |
| Spanien           | ES |
| Sri Lanka       | LK |
| St. Helena, Ascension, Tristan da Cunha | SH |
| Sudan           | SD |
| Suriname        | SR |
| Spitzbergen        | SJ |
| Schweden          | SE |
| Schweiz     | CH |
| Syrien           | SY |
| Taiwan          | TW |
| Tadschikistan      | TJ |
| Tansania        | TZ |
| Thailand        | TH |
| Timor-Leste     | TL |
| Togo            | TG |
| Tokelau         | TK |
| Tonga           | An |
| Trinidad und Tobago | TT |
| Tunesien         | TN |
| Türkei          | TR |
| Turkmenistan    | TM |
| Turks- und Caicosinseln | TC |
| Tuvalu          | TV |
| Amerikanische Überlinginseln | UM |
| Amerikanische Jungferninseln | VI |
| Uganda          | UG |
| Ukraine         | UA |
| Vereinigte Arabische Emirate | AE |
| Vereinigtes Königreich  | GB |
| Vereinigte Staaten   | US |
| Uruguay         | UY |
| Usbekistan      | UZ |
| Vanuatu         | VU |
| Vatikanstadt    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis und Futuna | WF |
| Jemen           | YE |
| Sambia          | ZM |
| Simbabwe        | ZW |


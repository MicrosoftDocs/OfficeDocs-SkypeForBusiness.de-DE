---
title: Direkte Routing-Landesvorwahl
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
description: Lesen Sie diesen Artikel, um die Landesvorwahl für den Medienpfad für das direkte Routing zu finden.
ms.openlocfilehash: 8607b6720104e743243851ad7edac20811ecd29f
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572212"
---
# <a name="direct-routing-media-path-country-codes"></a>Direct Routing-Medienpfad Landesvorwahl

Wenn Sie einen Routingpfad für Medien auswählen, weist das direkte Routing standardmäßig immer ein Datacenter auf der Grundlage der öffentlichen IP-Adresse des Session Border Controller (SBC) zu und wählt immer den Pfad aus, der dem SBC-Rechenzentrum am nächsten ist.

In einigen Fällen ist der Standard Medienpfad aber möglicherweise nicht der optimale Medienpfad. So kann beispielsweise eine öffentliche IP-Adresse aus einem United States-Bereich einem SBC in Europa zugewiesen werden. 

Mithilfe des-MediaRelayRoutingLocationOverride-Parameters mit den Cmdlets New-CsOnlinePSTNGateway und setCsOnlinePSTNGateway können Sie die bevorzugte Region für den Mediendatenverkehr angeben. Der folgende Befehl gibt beispielsweise an, dass die bevorzugte Region Deutschland ist:

Satz-CSOnlinePSTNGateway-Identity sbc1.contoso.com – MediaRelayRoutingLocationOverride de 

Beachten Sie, dass Microsoft nur empfiehlt, diesen Parameter festzulegen, wenn die Anrufprotokolle deutlich angeben, dass die Standardzuweisung des Datencenters für den Medienpfad nicht den Pfad verwendet, der dem SBC-Rechenzentrum am nächsten ist. 
 
## <a name="country-code-reference-table"></a>Ländercode-Referenztabelle

Die folgende Tabelle zeigt die Landesvorwahl Werte für den Parameter-MediaRelayRoutingLocationOverride:

| Land         | Code 
|-----------------|--------------------|
| Afghanistan     | AF |
| Aland-Inseln   | AX |
| Albanien         | Al |
| Algerien         | DZ |
| Amerikanisch-Samoa  | Als |
| Andorra         | AD |
| Angola          | Ao |
| Anguilla        | Al |
| Antarktis      | AQ | 
| Antigua und Barbuda | AG |
| Argentinien       | AR |
| Armenien         | Verwende |
| Aruba           | AW |
| Australien       | AU |
| Österreich         | Am |
| Aserbaidschan      | Arizona |
| Bahamas         | BS |
| Bahrain         | BH |
| Bangladesch      | BD |
| Barbados        | BB |
| Belarus         | BY |
| Belgien         | BE |
| Belize          | BZ |
| Benin           | Bj |
| Bermuda         | BM |
| Bhutan          | BT |
| Bolivien         | Bo |
| Bonaire         | BQ |
| Bosnien und Herzegowina | BA |
| Botswana        | BW |
| Bouvet-Insel   | BV |
| Brasilien          | BR |
| Britisches Territorium im indischen Ozean | IO |
| Britische Jungferninseln | VG |
| Brunei          | BN |
| Bulgarien        | BG |
| Burkina Faso    | BF |
| Burundi         | BI |
| Cabo Verde      | CV |
| Kambodscha        | KH |
| Kamerun        | CM |
| Kanada          | CA |
| Kaimaninseln  | KY |
| Zentralafrikanische Republik | CF |
| Tschad0            | TD |
| Chile           | CL |
| China           | CN |
| Weihnachtsinsel | CX |
| Kokosinseln (Keeling) | CC |
| Kolumbien        | CO |
| Komoren         | KM |
| Kongo           | CG |
| Kongo (DRC)     | CD |
| Cook-Inseln    | Tzung |
| Costa Rica      | CR |
| Elfenbeinküste   | CI |
| Kroatien         | HR |
| Kuba            | Ku |
| Curaçao         | CW |
| Zypern          | CY |
| Tschechien         | CZ |
| Dänemark         | DK |
| Dschibuti        | Moderator |
| Dominica        | DM |
| Dominikanische Republik | Tun |
| Ecuador         | EC |
| Ägypten           | EG |
| El Salvador     | SV |
| Äquatorialguinea | GQ |
| Eritrea         | Er |
| Estland         | EE |
| Eswatini        | SZ |
| Äthiopien        | ET |
| Falkland-Inseln | FK |
| Färöer   | ' |
| Fidschi            | FJ |
| Finnland         | FI |
| Frankreich          | FR |
| Französisch-Guyana   | GF |
| Französisch-Polynesien | PF |
| Französische Südliche Territorien | TF |
| Gabun           | GA |
| Gambia          | GM |
| Georgien         | GE |
| Deutschland         | DE |
| Ghana           | GH |
| Gibraltar       | GI |
| Griechenland          | Gr |
| Grönland       | GL |
| Grenada         | GD |
| Guadeloupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | Gy |
| Haiti           | Hallo |
| Heard-Insel und McDonald-Inseln | HM |
| Honduras        | HN |
| Hong Kong SAR (香港特別行政區)   | HK |
| Ungarn         | HU |
| Island         | Ist |
| Indien           | IN |
| Indonesien       | ID |
| Iran            | IR |
| Irak            | IQ |
| Irland         | IE |
| Isle of man     | Chat |
| Israel          | IL |
| Italien           | Es |
| Jamaika         | JM |
| Jan Mayen       | XJ |
| Japan           | JP |
| Jersey          | JE |
| Jordanien          | Jo |
| Kasachstan      | KZ |
| Kenia           | KE |
| Kiribati        | Ki |
| Korea           | KR |
| Kosovo0          | XK |
| Kuwait          | KW |
| Kirgisistan      | KG |
| Laos            | La |
| Lettland          | LV |
| Libanon         | LB |
| Lesotho         | LS |
| Liberia         | LR |
| Libyen           | LY |
| Liechtenstein   | Li |
| Litauen       | LT |
| Luxemburg      | LU |
| Macao SAR       | Mo |
| Madagaskar      | MG |
| Malawi          | MW |
| Malaysia        | MY |
| Malediven        | MV |
| Mali            | ML |
| Malta           | MT |
| Marshall-Inseln | MH |
| Martinique      | MQ |
| Mauretanien      | Mr |
| Mauritius       | Mu |
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
| Nauru0           | Nr |
| Nepal           | NP |
| Niederlande     | NL |
| Neukaledonien   | NC |
| Neuseeland     | NZ |
| Nicaragua       | NI |
| Niger           | NE |
| Nigeria         | NG |
| Niue            | Nu |
| Norfolk-Insel  | NF |
| Nordkorea     | KP |
| Nord-Mazedonien | MK |
| Nördliche Marianen | NP |
| Norwegen          | Nein |
| Oman            | OM |
| Pakistan        | PK |
| Palau           | PW |
| Palästinensische Autonomiebehörde | PS |
| Panama          | PA |
| Papua-Neuguinea | Bild |
| Paraguay        | PY |
| Peru            | PE |
| Philippinen     | PH |
| Pitcairn-Inseln | TN |
| Polen          | PL |
| Portugal        | PT |
| Puerto Rico     | PR |
| Katar           | QA |
| Réunion         | Wieder |
| Rumänien         | RO |
| Russland          | RU |
| Ruanda          | RW |
| Saba            | XS |
| Saint Barthelemy | BL |
| St. Kitts und Nevis | KN |
| St. Lucia     | LC |
| Saint Martin    | MF |
| Saint Pierre und Miquelon | PM |
| St. Vicent und die Grenadinen | VC |
| Samoa           | WS |
| San Marino      | SM |
| Sao Tome und Principe | St |
| Saudi Arabia (المملكة العربية السعودية)    | SA |
| Senegal         | SN |
| Serbien          | RS |
| Seychellen      | SC |
| Sierra Leone    | SL | 
| Singapur       | SG |
| Sint Eustatius  | Xe |
| Sint Maarten    | SX |
| Slowakei        | SK |
| Slowenien        | SL |
| Solomon-Inseln | SB |
| Somalia0         | Also |
| Südafrika    | ZA |
| Südgeorgien und Süd-Sandwich-Inseln | GS |
| Südsudan     | SS |
| Spanien           | ES |
| Sri Lanka       | LK |
| St. Helena, Ascension, Tristan da Cunha | SH |
| Sudan           | SD |
| Surinam        | SR |
| Svalbard        | SJ |
| Schweden          | SE |
| Schweiz     | CH |
| Syrien           | Sy |
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
| Turks-und Caicos-Inseln | TC |
| Tuvalu          | TV |
| US-amerikanische abgelegene Inseln | UM |
| US-amerikanische Jungferninseln | VI |
| Uganda          | UG |
| Ukraine         | UA |
| Vereinigte Arabische Emirate | AE |
| Vereinigtes Königreich  | GB |
| Vereinigte Staaten   | USA |
| Uruguay         | UY |
| Usbekistan      | UZ |
| Vanuatu0         | VU |
| Vatikanstadt    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis und Futuna | WF |
| Jemen           | Ihr |
| Sambia          | ZM |
| Simbabwe        | ZW |


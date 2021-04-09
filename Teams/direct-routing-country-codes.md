---
title: Ländercodes für direktes Routing
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
description: Lesen Sie diesen Artikel, um nach Den Medienpfad-Ländercodes für Direct Routing zu suchen, damit Sie den optimalen Medienpfad auswählen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56cdc48b33e048776a43a37864930fc153c47aac
ms.sourcegitcommit: c80af314f1a573f99dd66858301c004ccc5410d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51648124"
---
# <a name="direct-routing-media-path-country-codes"></a>Direct Routing Media Path Country Codes

Bei der Auswahl eines Routingpfads für Medien weist Direct Routing standardmäßig immer ein Rechenzentrum basierend auf der öffentlichen IP-Adresse des Session Border Controllers (SBC) zu und wählt immer den Pfad aus, der dem SBC-Rechenzentrum am nächsten ist.

In einigen Fällen ist der Standardmedienpfad jedoch möglicherweise nicht der optimale Medienpfad. So könnte beispielsweise eine öffentliche IP aus einem Bereich der VEREINIGTEn Staaten einem SBC in Europa zugewiesen werden. 

Mithilfe des -MediaRelayRoutingLocationOverride-Parameters mit den cmdlets New-CsOnlinePSTNGateway und Set-CsOnlinePSTNGateway können Sie den bevorzugten Bereich für den Mediendatenverkehr angeben. Der folgende Befehl gibt beispielsweise an, dass die bevorzugte Region Deutschland ist:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Beachten Sie, dass Microsoft das Festlegen dieses Parameters nur empfiehlt, wenn die Anrufprotokolle deutlich angeben, dass die Standardzuordnung des Rechenzentrums für den Medienpfad nicht den Pfad verwendet, der dem SBC-Rechenzentrum am nächsten ist. 

> [!NOTE]
> -MediaRelayRoutingLocationOverride – Dieser Befehl steht in Szenarien für direktes Routing nicht zur Verfügung.
 
## <a name="country-code-reference-table"></a>Ländercodereferenztabelle

Die folgende Tabelle zeigt die Ländercodewerte für den Parameter -MediaRelayRoutingLocationOverride:

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
| BouvetInsel   | BV |
| Brasilien          | BR |
| Britisches Territorium im Indischen Ozean | IO |
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
| Zentralafrika | CF |
| Chad            | TD |
| Chile           | CL |
| China           | CN |
| Weihnachtsinsel | CX |
| Kokosinseln (Keelinginseln) | CC |
| Kolumbien        | CO |
| Komoren         | KM |
| Kongo           | CG |
| Kongo (DRK)     | CD |
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
| Eswatini        | SZ |
| Äthiopien        | ET |
| Falklandinseln | FK |
| Färöer   | FO |
| Fidschi            | FJ |
| Finnland         | FI |
| Frankreich          | FR |
| Französisch-Guayana   | GF |
| Französisch-Polynesien | PF |
| Französische Südgebiete | TF |
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
| Guyana          | GY |
| Haiti           | Hallo |
| Heard Island and McDonald Islands | HM |
| Honduras        | HN |
| Hongkong (SAR)   | HK |
| Ungarn         | HU |
| Island         | IS |
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
| Kosovo          | XK |
| Kuwait          | KW |
| Kirgisistan      | KG |
| Laos            | LA |
| Lettland          | LV |
| Libanon         | LB |
| Lesotho         | LS |
| Liberia         | LR |
| Libyen           | LY |
| Liechtenstein   | LI |
| Litauen       | LT |
| Luxemburg      | LU |
| Macao SAR       | MO |
| Madagaskar      | MG |
| Malawi          | MW |
| Malaysia        | MY |
| Malediven        | MV |
| Mali            | ML |
| Malta           | MT |
| Marshall-Inseln | MH |
| Martinique      | MQ |
| Mauretanien      | MR |
| Mauritius       | MU |
| Mayotte         | YT |
| Mexiko          | MX |
| Mikronesien      | FM |
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
| Nordkorea     | KP |
| Nordmakedonien | MK |
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
| PitcairnInseln | PN |
| Polen          | PL |
| Portugal        | PT |
| Puerto Rico     | PR |
| Katar           | QA |
| Reunion         | RE |
| Rumänien         | RO |
| Russland          | RU |
| Ruanda          | RW |
| Saba            | XS |
| St. Barthelemy | BL |
| St. Kitts und Nevis | KN |
| St. Lucia     | LC |
| St. Martin    | MF |
| Saint Pierre und Miquelon | PM |
| St. Vincent und die Grenadinen | VC |
| Samoa           | WS |
| San Marino      | SM |
| Sao Tome und Principe | ST |
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
| Somalia         | Also |
| Südafrika    | ZA |
| Südgeorgien und Südliche Sandwichinseln | GS |
| Südsudan     | SS |
| Spanien           | ES |
| Sri Lanka       | LK |
| St. Helena, Himmelfahrt, Tristan da Cunha | SH |
| Sudan           | SD |
| Suriname        | SR |
| Svalbard        | SJ |
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
| Us.Outlying Islands | UM |
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


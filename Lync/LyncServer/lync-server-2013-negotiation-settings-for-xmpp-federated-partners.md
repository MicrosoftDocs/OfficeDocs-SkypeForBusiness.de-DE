---
title: 'Lync Server 2013: Aushandlungs Einstellungen für XMPP-Verbundpartner'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505592"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Aushandlungs Einstellungen für XMPP-Verbundpartner in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

Die Einstellungen für die Aushandlungstypen in der Konfiguration eines XMPP-Partners können die unterschiedlichsten Kombinationen annehmen. Doch nicht alle diese Kombinationen sind gültig. In der Tabelle in diesem Abschnitt werden die gültigen und die ungültigen Einstellungen beschrieben. Gängige Konfigurationen sind in der ersten Tabelle enthalten, die zweite Tabelle ist eine Auflistung aller möglichen Kombinationen. Beachten Sie, dass Sie keine *Simple Authentication and Security Layer* (SASL) haben können, **es sei denn** , *Transport Layer Security* (TLS) ist ebenfalls verfügbar. SASL wird in einem unverschlüsselten (lesbaren) Format gesendet und sollte nie übertragen werden, es sei denn, es besteht Schutz durch einen anderen Mechanismus wie etwa TLS.

### <a name="common-xmpp-federation-negotiation-methods"></a>Gängige XMPP-Partnerverbund-Aushandlungsmethoden

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport Layer Security (TLS)</th>
<th>Simple Authentication and Security Layer (SASL)</th>
<th>Rückrufauthentifizierung</th>
<th>Erwartete Authentifizierungsmethode(n)</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><p>Wenn TLS und SASL auf Erforderlich festgelegt werden, kann damit sichergestellt werden, dass der SASL-Nachrichtenstream sicher ist. Rückruf ist nicht verfügbar und kann nicht für eine Fallbackmethode verwendet werden, wenn für den XMPP-Verbundpartner TLS nicht auf Erforderlich oder Optional festgelegt ist.</p></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>Richtig</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><p>Wenn TLS auf Erforderlich festgelegt wird, wird SASL verwendet, wenn für den XMPP-Verbundpartner SASL auf Optional oder Erforderlich festgelegt ist. Ist SASL nicht verfügbar, wird Rückruf über TLS verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Optional</p></td>
<td><p>Richtig</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><p>Diese Einstellungen sind zwar sehr flexibel hinsichtlich der angebotenen Aushandlungsmethoden, erfordern aber die Einstellungen des XMPP-Verbundpartners. Wenn für den Partner TLS auf Optional oder Erforderlich festgelegt ist, SASL aber nicht unterstützt wird, ist TLS-Rückruf verfügbar. Wenn für den Partner TLS und SASL auf Optional oder Erforderlich festgelegt sind, wird die optimale Auswahl von TLS über SASL verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Richtig</p></td>
<td><p>TCP-Rückruf</p></td>
<td><p>In vielen Fällen ist TCP-Rückruf die einzig mögliche Lösung. Das ist zwar weniger optimal als andere Optionen, bietet aber ein bestimmtes Maß an Vertrauenswürdigkeit.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>Schema der XMPP-Partnerverbund-Aushandlungsmethoden (vollständig)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Transport Layer Security (TLS)</th>
<th>Simple Authentication and Security Layer (SASL)</th>
<th>Rückrufauthentifizierung</th>
<th>Erwartete Authentifizierungsmethode</th>
<th>Anmerkungen, Warnung oder Fehler wegen ungültiger Konfiguration</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>Richtig</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]  
> Rückruf funktioniert nicht, wenn sowohl SASL als auch TLS erforderlich ist.


</div></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Erforderlich</p></td>
<td><p>Richtig</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Erforderlich</p></td>
<td><p>Richtig</p></td>
<td><p>TCP-Rückruf</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Erforderlich</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Ungültige Konfiguration


</div></td>
<td><div>

> [!WARNING]  
> Da SASL TLS erfordert und TLS nicht verfügbar ist, SASL/TLS kann nicht erfolgreich sein. TCP-Rückruf ist auf False festgelegt und kann nicht verwendet werden.


</div></td>
</tr>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>Richtig</p></td>
<td><p>SASL über TLS, TLS-Rückruf</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Optional</p></td>
<td><p>Richtig</p></td>
<td><p>SASL über TLS, TLS-Rückruf, TCP-Rückruf</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Optional</p></td>
<td><p>False</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Optional</p></td>
<td><p>Richtig</p></td>
<td><p>TCP-Rückruf</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Optional</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> Ungültige Konfiguration


</div></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn TLS optional sein darf, kann dies zu Fehlern bei Sitzungsaushandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Richtig</p></td>
<td><p>TLS-Rückruf</p></td>
<td><p>Konfiguration erlaubt TLS-Rückruf.</p></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>False</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]  
> SASL oder Rückruf muss aktiviert sein.


</div></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Richtig</p></td>
<td><p>TLS-Rückruf, TCP-Rückruf</p></td>
<td><p>Je nach den Aushandlungsoptionen am anderen Endpunkt wird TCP- oder TLS-Rückruf akzeptiert.</p></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>False</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]  
> SASL oder Rückruf muss aktiviert sein.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Richtig</p></td>
<td><p>TCP-Rückruf</p></td>
<td><p>TCP-Rückruf ist die einzige verfügbare Aushandlungsmethode</p></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>False</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]  
> SASL oder Rückruf muss aktiviert sein.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


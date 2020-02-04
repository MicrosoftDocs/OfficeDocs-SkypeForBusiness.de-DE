---
title: 'Lync Server 2013: Aushandlungseinstellungen für XMPP-Verbundpartner'
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
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Aushandlungseinstellungen für XMPP-Verbundpartner in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Die Einstellungen für die Aushandlungs Typen in der Konfiguration eines XMPP-Partners haben eine Vielzahl möglicher Kombinationen. Nicht alle diese Kombinationen sind gültig. In der in diesem Thema beschriebenen Tabelle werden die gültigen und ungültigen Einstellungen definiert. Allgemeine Konfigurationen werden in der ersten Tabelle dargestellt, der zweiten Tabelle, in der alle möglichen Kombinationen aufgeführt sind. Beachten Sie, dass Sie keine *einfache Authentifizierungs-und Sicherheitsschicht* (SASL) haben können, **es sei denn** , *Transport Layer Security* (TLS) steht ebenfalls zur Verfügung. SASL wird in einem unverschlüsselten (lesbaren) Format gesendet und sollte niemals übertragen werden, es sei denn, es wird durch ein anderes Mittel wie TLS geschützt.

### <a name="common-xmpp-federation-negotiation-methods"></a>Allgemeine Methoden zur XMPP-Föderations Verhandlung

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
<th>Einfache Authentifizierungs-und Sicherheitsschicht (SASL)</th>
<th>Dialback-Authentifizierung</th>
<th>Erwartete Authentifizierungsmethode (n)</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p> Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>Falsch</p></td>
<td><p>SASL über TLS</p></td>
<td><p>TLS und SASL sind hilfreich, um sicherzustellen, dass der SASL-Nachrichtendatenstrom sicher ist. Dialback ist nicht verfügbar und kann nicht für eine Fallback-Methode verwendet werden, wenn der XMPP-Verbundpartner TLS nicht auf Required oder optional gesetzt hat.</p></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>Wahr</p></td>
<td><p>SASL über TLS, TLS-Dialback, TCP-Dialback</p></td>
<td><p>Wenn der XMPP-Föderationspartner SASL auf optional oder erforderlich SASL gesetzt hat, wird eine TLS-Anforderung verwendet. Wenn SASL nicht zur Verfügung steht, wird Dialback über TLS verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>Optional </p></td>
<td><p>Optional</p></td>
<td><p>Wahr</p></td>
<td><p>SASL über TLS, TLS-Dialback, TCP-Dialback</p></td>
<td><p>Obwohl die angebotenen Verhandlungsmethoden sehr flexibel sind, basieren diese Einstellungen auf den Einstellungen des XMPP-Verbundpartners. Wenn der Partner TLS optional oder erforderlich hat, aber SASL nicht unterstützt wird, steht TLS-Dialback zur Verfügung. Wenn der Partner TLS und SASL auf optional oder required eingestellt hat, wird die optimale Auswahl von TLS über SASL verwendet.</p></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Wahr</p></td>
<td><p>TCP-Dialback</p></td>
<td><p>In vielen Fällen ist TCP-Dialback die einzige mögliche Lösung. Weniger wünschenswert als andere Optionen, bietet dies ein gewisses Maß an Vertrauen.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP-Verbund-Aushandlungs Methoden-Matrix – abgeschlossen

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
<th>Einfache Authentifizierungs-und Sicherheitsschicht (SASL)</th>
<th>Dialback-Authentifizierung</th>
<th>Erwartete Authentifizierungsmethode</th>
<th>Hinweise, Warnung oder Fehler für ungültige Konfiguration</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p> Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>Wahr</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]  
> Dialback wird nicht ausgeführt, wenn sowohl SASL als auch TLS erforderlich sind.


</div></td>
</tr>
<tr class="even">
<td><p> Erforderlich</p></td>
<td><p>Erforderlich</p></td>
<td><p>Falsch</p></td>
<td><p>SASL über TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Erforderlich</p></td>
<td><p>Wahr</p></td>
<td><p>SASL über TLS, TLS-Dialback, TCP-Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Erforderlich</p></td>
<td><p>Falsch</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Erforderlich</p></td>
<td><p>Wahr</p></td>
<td><p>TCP-Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Erforderlich</p></td>
<td><p>Falsch</p></td>
<td><div>

> [!WARNING]  
> Ungültige Konfiguration


</div></td>
<td><div>

> [!WARNING]  
> Da SASL TLS erfordert und TLS nicht zur Verfügung steht, kann SASL/TLS nicht erfolgreich sein. TCP Dialback ist auf "false" festgelegt und kann nicht verwendet werden.


</div></td>
</tr>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>Wahr</p></td>
<td><p>SASL über TLS, TLS-Dialback</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Optional</p></td>
<td><p>Falsch</p></td>
<td><p>SASL über TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Optional </p></td>
<td><p>Optional</p></td>
<td><p>Wahr</p></td>
<td><p>SASL über TLS, TLS-Dialback, TCP-Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Optional </p></td>
<td><p>Optional</p></td>
<td><p>Falsch</p></td>
<td><p>SASL über TLS</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Optional</p></td>
<td><p>Wahr</p></td>
<td><p>TCP-Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.


</div></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Optional</p></td>
<td><p>Falsch</p></td>
<td><div>

> [!WARNING]  
> Ungültige Konfiguration


</div></td>
<td><div>

> [!WARNING]  
> SASL erfordert TLS. Wenn Sie zulassen, dass TLS optional ist, kann dies zu fehlgeschlagenen Sitzungs Verhandlungen führen.


</div></td>
</tr>
<tr class="odd">
<td><p>Erforderlich</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Wahr</p></td>
<td><p>TLS-Dialback</p></td>
<td><p>Die Konfiguration ermöglicht TLS-Dialback.</p></td>
</tr>
<tr class="even">
<td><p>Erforderlich</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Falsch</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]  
> SASL oder Dialback muss aktiviert sein.


</div></td>
</tr>
<tr class="odd">
<td><p>Optional</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Wahr</p></td>
<td><p>TLS-Dialback, TCP-Dialback</p></td>
<td><p>Basierend auf den Aushandlungs Optionen des anderen Endpunkts werden TCP-oder TLS-Dialback akzeptiert.</p></td>
</tr>
<tr class="even">
<td><p>Optional</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Falsch</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]  
> SASL oder Dialback muss aktiviert sein.


</div></td>
</tr>
<tr class="odd">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Wahr</p></td>
<td><p>TCP-Dialback</p></td>
<td><p>TCP-Dialback ist die einzige verfügbare Aushandlungsmethode.</p></td>
</tr>
<tr class="even">
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Falsch</p></td>
<td><p>Ungültige Konfiguration</p></td>
<td><div>

> [!WARNING]  
> SASL oder Dialback muss aktiviert sein.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


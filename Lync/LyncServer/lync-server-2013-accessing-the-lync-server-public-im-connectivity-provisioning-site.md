---
title: Zugreifen auf die Lync Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chatdiensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Zugreifen auf die Lync Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chatdiensten von Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2019-03-22_

Der Bereitstellungsprozess für lync-Skype-Konnektivität hat sich im Vergleich zu früheren PIC-Bereitstellungsmethoden geändert. Dieser Bereitstellungsprozess kann bis zu dreißig Tage dauern. Wir empfehlen, diesen Prozess zuerst zu starten und dann die verbleibenden Schritte in diesem Dokument auszuführen. Nachdem der lync-Skype-Bereitstellungsprozess für Ihr Konto abgeschlossen ist, wird das Konto aktiviert, und ihre berechtigten Benutzer sind für öffentliche Chat Verbindungen aktiviert.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Zur Bereitstellung von lync-Skype-Konnektivität benötigen Sie die folgenden Informationen:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Die Microsoft-Vertragsnummer</p></li>
<li><p>Den vollqualifizierten Domänenname (Fully Qualified Domain Name, FQDN) des Zugriffs-Edgediensts</p></li>
<li><p>SIP-Domäne/n (Session Initiation Protocol)</p></li>
<li><p>FQDNs für alle zusätzlichen Zugriffs-Edgedienste</p></li>
<li><p>Kontaktinformationen</p></li>
</ol></td>
</tr>
</tbody>
</table>

Ab April 2019 werden wir die Erfassung und Speicherung von Kontaktinformationen für Kunden, die über die PIC.lync.com-Website für Skype Federation bereitgestellt werden, beenden. Diese Änderung wird vorgenommen, um sicherzustellen, dass das PIC.lync.com-Bereitstellungssystem den Microsoft-Datenschutzrichtlinien entspricht. 

Sobald diese Änderung in Echtzeit erfolgt, können wir keine e-Mail-Updates mehr für ausstehende Bereitstellungsänderungen bereitstellen. PIC-Bereitstellungsänderungen werden in der Regel innerhalb von 24-48 Stunden nach der Eingabe abgeschlossen. Wenn Sie nach dem Einreichen einer Bereitstellungsanfrage nach wie vor Skype Federation Issues (48) erleben, wenden Sie sich bitte an den technischen Support von Microsoft, um weitere Informationen zu erhalten.

> [!IMPORTANT]
> Im Rahmen dieser Änderung werden alle zuvor eingegebenen Kontaktinformationen bis Ende April 2019 aus unserem System gelöscht.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>So initiieren Sie den Bereitstellungsprozess für lync-Skype-Konnektivität:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Registrieren Sie sich mit Ihrer Microsoft <strong>https://pic.lync.com</strong>Windows Live ID bei der Website.</p></li>
<li><p>Wählen Sie den Typ Ihres Microsoft-Lizenzvertrags aus.</p></li>
<li><p>Aktivieren Sie das Kontrollkästchen, um sicherzustellen, dass Sie die Produkt Nutzungsrechte für lync Server gelesen und akzeptiert haben.</p></li>
<li><p>Klicken Sie auf der Seite <strong>Bereitstellungsanforderung initiieren</strong> auf den entsprechenden Link, um eine Bereitstellungsanforderung zu initiieren:</p></li>
<li><p>Geben Sie auf der Seite <strong>Bereitstellungsinformationen angeben</strong> den <strong>FQDN des Access-Edgedienst</strong>ein. Beispiel: <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Nach dem 1. Juli 2017 Microsoft zusätzlich für Kunden den Verbund-DNS-SRV-Eintrag bereitgestellt, der für die Verbindung mit öffentlichen Chat Diensten bereitgestellt wird.

</li>
<li><p>Geben Sie mindestens einen SIP-Domänennamen ein, und klicken Sie dann auf <strong>Hinzufügen</strong>.</p>



> [!IMPORTANT]
> Mindestens ein Access Edge-Server und eine SIP-Domäne sind erforderlich, um den Bereitstellungsprozess abzuschließen. SIP-Domäne und Zugriffs-Edge-Server müssen aktiv, betriebsbereit und im Netzwerk erreichbar sein.

</li>
<li><p>Wählen Sie in der Liste der <strong>öffentlichen Chatdienst Anbieter</strong> <strong>Skype aus,</strong> und klicken Sie auf <strong>weiter</strong> , um Kontaktinformationen hinzuzufügen, und übermitteln Sie die Bereitstellungsanforderung.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Nachdem die Bereitstellungsanforderung übermittelt wurde, kann es bis zu 30 Tage dauern, bis das Konto aktiviert ist und die Benutzer für die öffentliche Chat Verbindung aktiviert werden.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren von Partnerverbünden und Verbindungen mit öffentlichen Chatdiensten (PIC)

Nachdem Sie die Bereitstellungsanforderung übermittelt haben, können Sie sich auf die lync Server-Umgebung und die administrativen Aufgaben konzentrieren, die zum Konfigurieren der lync-Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der lync Server-Administrator lync Server bereitgestellt und den externen Zugriff konfiguriert hat. Weitere Informationen zum Konfigurieren von externem Zugriff für lync Server finden Sie unter "Planen des Zugriffs für externe [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) Benutzer" unter und "Bereitstellen des [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)Zugriffs auf externe Benutzer" unter.

Um die lync Server-Umgebung für lync-Skype-Konnektivität vorzubereiten, muss der lync Server-Administrator die folgenden drei Aufgaben ausführen:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Konfigurieren des Partnerverbunds und der PIC

Föderation ist erforderlich, um Skype-Benutzern die Kommunikation mit lync-Benutzern in Ihrer Organisation zu ermöglichen. PIC (Public Instant Messaging Connectivity) ist eine Klasse des Verbandes und muss so konfiguriert sein, dass Ihre lync-Nutzer mit Skype-Nutzern kommunizieren können. Föderation und PIC werden mithilfe der lync Server-Systemsteuerung konfiguriert (siehe unten).

<div>


> [!IMPORTANT]
> Der PIC-Partnerverbund wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt. Zu den unterstützten Plattformen für die PIC-Föderation gehören lync Server 2013, lync Server 2010 und Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund

Mithilfe der lync Server-Systemsteuerung muss ein Administrator mindestens eine Richtlinie für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Konfigurieren der Skype PIC-Anbieter Einstellung für lync

Mithilfe der lync Server-Verwaltungsshell muss ein Administrator die lync-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird.

<div>


> [!NOTE]
> Benutzer von PIC-Dienstanbietern können erst dann an Chatunterhaltungen oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie zudem mindestens eine Richtlinie (Schritt 2 an früherer Stelle in diesem Verfahren) zur Unterstützung der Verbindung mit öffentlichen Chatanbietern konfiguriert haben. <BR>Informationen zum Konfigurieren von Verbund und PIC finden Sie unter "aktivieren oder Deaktivieren von <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>Verbund-und öffentlichen Chat Verbindungen" unter.<BR>Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern finden Sie unter "Konfigurieren von Richt <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>Linien zum Steuern des Zugriffs öffentlicher Benutzer" unter.



</div>

1.  Öffnen Sie auf einem lync Server-Front-End-Server die lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden beiden Befehle aus:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Wenn Sie nicht bereits über einen PIC-Anbieter in Ihrer Umgebung verfügen und einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet <STRONG>Remove-CsPublicProvider</STRONG> nicht ausführen.

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > In lync Server 2013 CU5 &amp; lync-Desktop Client in Office 2013 SP1 wurde die Situation verbessert, in der lync-Benutzer Skype-Kontakte hinzufügen, um nicht-Microsoft-Domänen zu "schmücken", um Sie zu identifizieren und an Skype weiterzuleiten (das Format von: User (contoso. com) @MSN. com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der im Dialogfeld „Skype-Kontakt hinzufügen“ eingegebenen Benutzeradresse mit dem Parameter „NameDecorationRoutingDomain“ (der auf „msn.com“ festgelegt sein sollte), wenn die Domänen nicht im Parameter „NameDecorationExcludedDomainList“ enthalten sind (zurzeit werden „msn.com“, „live.com“, „Hotmail.com“ und „outlook.com“ unterstützt).

        
        </div>

3.  Von einem lync-Client aus können Sie nun Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie sein Microsoft-Konto angeben. Darüber hinaus kann ein Skype-Nutzer, der sich mit seinem Microsoft-Konto zusammengeführt und angemeldet hat, Kontaktanfragen an lync-Nutzer senden. Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Weitere Informationen zum Hinzufügen von Clients zu lync finden Sie unter [Verwenden der lync-Skype-Konnektivität in lync Server 2013 als Endbenutzer](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Detaillierte Informationen zum Ändern von gehosteten Anbietern finden Sie unter "erstellen oder Bearbeiten von gehosteten SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)-Verbund Anbietern" unter.

Damit sind die Verwaltungsaufgaben abgeschlossen, die auf dem Server durchgeführt werden müssen. Sie sind jetzt für die lync-Skype-Konnektivität eingerichtet.

</div>

</div>

<div>

## <a name="additional-resources"></a>Weitere Ressourcen

[Verwenden von Lync-Skype-Konnektivität als Endbenutzer in Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Leitfaden für die Bereitstellung der Lync-Skype-Konnektivität in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


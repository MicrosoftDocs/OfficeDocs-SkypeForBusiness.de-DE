---
title: Zugreifen auf die lync Server-Website für die Konnektivität mit öffentlichen Instant Messaging-Diensten
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
ms.openlocfilehash: 4e57bac3460c8feb5b3417f433aa228825d824a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529752"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Zugreifen auf die lync Server-Website für die Konnektivität von öffentlichen Instant Messaging-Diensten von lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2019-03-22_

Der Bereitstellung-Prozess für Lync-Skype Konnektivität wurde im Vergleich zu früheren PIC-Bereitstellung Methoden geändert. Dieser Bereitstellung Vorgang kann bis zu dreißig Tage dauern. Es wird empfohlen, dass Sie zuerst diesen Prozess starten, bevor Sie die restlichen Schritte in diesem Dokument abschließen. Nachdem der Lync-Skype Bereitstellung für Ihr Konto abgeschlossen wurde, wird das Konto aktiviert, und die berechtigten Benutzer sind für die Verbindung mit öffentlichen Chat Diensten aktiviert.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Um Lync-Skype Konnektivität anbieten zu können, benötigen Sie die folgenden Informationen:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft-Vertragsnummer</p></li>
<li><p>Zugriffs-Edgedienst vollqualifizierter Domänenname (FQDN)</p></li>
<li><p>SIP (Session Initiation Protocol)-Domäne (n)</p></li>
<li><p>Alle zusätzlichen Zugriffs-Edgedienst FQDNs</p></li>
<li><p>Kontaktinformationen</p></li>
</ol></td>
</tr>
</tbody>
</table>

Ab April 2019 werden wir die Erfassung und Aufbewahrung von Kontaktinformationen für Kunden beenden, die über die PIC.lync.com-Website für Skype Federation vorgesehen sind. Diese Änderung wird vorgenommen, um sicherzustellen, dass das PIC.lync.com-Bereitstellung System den Microsoft-Datenschutzrichtlinien entspricht. 

Sobald diese Änderung aktiv ist, können wir keine e-Mail-Updates mehr für ausstehende Bereitstellung Änderungen bereitstellen. PIC-prodie Änderungen werden normalerweise innerhalb von 24-48 Stunden nach der Eingabe abgeschlossen. Wenn Sie noch immer Probleme mit dem Skype-Verbund haben 48 Stunden nach dem Einreichen einer proprovisionierung, wenden Sie sich an den technischen Support von Microsoft, um weitere Informationen zu erhalten.

> [!IMPORTANT]
> Im Rahmen dieser Änderung werden alle zuvor eingegebenen Kontaktinformationen bis Ende April 2019 aus unserem System gelöscht.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>So initiieren Sie den Bereitstellung-Prozess für Lync-Skype Konnektivität:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Melden Sie sich mit <strong>https://pic.lync.com</strong> Ihrer Microsoft Windows Live ID bei der Website an.</p></li>
<li><p>Wählen Sie den Typ Microsoft-Lizenzvertrag aus.</p></li>
<li><p>Aktivieren Sie das Kontrollkästchen, um sicherzustellen, dass Sie die Produktnutzungsrechte für lync Server gelesen und akzeptiert haben.</p></li>
<li><p>Klicken Sie auf der Seite zum <strong>Initiieren einer proaktivierungs Anforderung</strong> auf den entsprechenden Link, um eine Anforderung für die Weiterleitung zu initiieren:</p></li>
<li><p>Geben Sie auf der Seite <strong>Informationen zur Datenangabe angeben</strong> den <strong>Zugriffs-Edgedienst FQDN</strong>ein. Beispiel: <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Nach dem 1. Juli 2017 Microsoft außerdem, dass Kunden den Verbund-DNS-SRV-Eintrag für öffentliche Chat Verbindungen bereitstellen müssen, damit Sie weiterhin funktionieren.

</li>
<li><p>Geben Sie mindestens einen SIP-Domänennamen ein, und klicken Sie dann auf <strong>Hinzufügen</strong>.</p>



> [!IMPORTANT]
> Mindestens ein Zugriffs-Edgeserver und eine SIP-Domäne sind erforderlich, um den Bereitstellung-Prozess abzuschließen. Die SIP-Domäne und der Zugriffs-Edgeserver müssen aktiv, funktionsfähig und im Netzwerk erreichbar sein.

</li>
<li><p>Wählen Sie in der Liste der <strong>öffentlichen Sofortnachrichten-Dienstanbieter</strong> <strong>Skype aus,</strong> und klicken Sie auf <strong>weiter</strong> , um Kontaktinformationen hinzuzufügen, und senden Sie die Anforderung für die Bereitstellung.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Nachdem die Übermittlungsanforderung übermittelt wurde, kann es bis zu 30 Tage dauern, bis das Konto aktiviert ist und Benutzer für die Verbindung mit öffentlichen Chat Diensten aktiviert werden können.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren von Verbund-und Public Chat-Konnektivität (PIC)

Nachdem Sie die Bereitstellung angefordert haben, können Sie sich auf die lync Server Umgebung und die administrativen Aufgaben konzentrieren, die zum Konfigurieren Lync-Skype Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der lync Server Administrator lync Server bereitgestellt und den externen Zugriff konfiguriert hat. Weitere Informationen zum Konfigurieren des externen Zugriffs für lync Server finden Sie unter "Planen des Zugriffs durch externe Benutzer" unter [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) und "Bereitstellen des Zugriffs auf externe Benutzer" unter [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) .

Um die lync Server Umgebung für Lync-Skype Konnektivität vorzubereiten, muss der lync Server Administrator die folgenden drei Aufgaben ausführen:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Konfigurieren von Partnerverbund und PIC

Partnerverbund ist erforderlich, damit Skype-Benutzer mit lync-Benutzern in Ihrer Organisation kommunizieren können. Die öffentliche Instant Messaging-Konnektivität (PIC) ist eine Klasse des Verbunds und muss so konfiguriert sein, dass Ihre lync-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe der lync Server-Systemsteuerung, unten dargestellt, konfiguriert.

<div>


> [!IMPORTANT]
> PIC Federation wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt. Die unterstützten Plattformen für den PIC-Verbund umfassen lync Server 2013, lync Server 2010 und Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer

Mit dem lync Server-Systemsteuerung muss ein Administrator eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Konfigurieren der Skype PIC-Anbieter Einstellung für lync

Mit dem lync Server-Verwaltungsshell muss ein Administrator die lync-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird.

<div>


> [!NOTE]
> Benutzer von PIC-Dienstanbietern (Public Instant Messaging Connectivity) können nicht an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) für die Unterstützung von Verbindungen mit öffentlichen Chat Diensten konfiguriert haben.<BR>Informationen zum Konfigurieren von Partnerverbund und PIC finden Sie unter "aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> .<BR>Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer finden Sie unter "configure Policies to Control Public User Access" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> .



</div>

1.  Öffnen Sie in einer lync Server Front-End-Server die lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden zwei Befehle aus:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Wenn in Ihrer Umgebung noch kein PIC-Anbieter vorhanden ist und Sie einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet <STRONG>Remove-CsPublicProvider</STRONG> nicht ausführen.

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > In lync Server 2013 CU5 &amp; lync-Desktop-Client in Office 2013 SP1 hinzugefügt, verbessern NameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, in der lync-Benutzer Skype-Kontakte hinzufügen, um nicht-Microsoft-Domänen zu "dekorieren", um diese zu identifizieren und an Skype weiterzuleiten (das Format: User (contoso. com) @MSN. com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der Adresse des Benutzers eingeben im Dialogfeld "Skype-Kontakt hinzufügen" mit dem NameDecorationRoutingDomain (die auf MSN.com festgelegt werden sollte), wenn Sie nicht die Domänen im NameDecorationExcludedDomainList enthält (wir können derzeit MSN.com, Live.com, hotmail.com, Outlook.com) unterstützen.

        
        </div>

3.  Von einem lync-Client aus können Sie nun Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie Ihr Microsoft-Konto angeben. Darüber hinaus kann ein Skype-Benutzer, der sich mit seinem Microsoft-Konto zusammengeführt und angemeldet hat, Kontaktanfragen an lync-Benutzer senden. Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Weitere Informationen zum Hinzufügen von Clients zu lync finden Sie unter [using Lync-Skype Connectivity in lync Server 2013 as a End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Ausführliche Informationen zum Ändern gehosteter Anbieter finden Sie unter "erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern" unter [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .

Dadurch werden die administrativen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen. Sie sind nun für Lync-Skype Konnektivität eingerichtet.

</div>

</div>

<div>

## <a name="additional-resources"></a>Weitere Ressourcen

[Verwenden Lync-Skype Konnektivität in lync Server 2013 als Endbenutzer](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Leitfaden zur Anleitung zur Lync-Skype Konnektivität in lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


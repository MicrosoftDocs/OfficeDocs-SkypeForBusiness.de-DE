---
title: 'Lync Server 2013: Zugreifen auf die Lync Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chatdiensten'
TOCTitle: Zugreifen auf die Lync Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chatdiensten
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn440174(v=OCS.15)
ms:contentKeyID: 59373609
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zugreifen auf die Lync Server-Bereitstellungswebsite für Verbindungen mit öffentlichen Chatdiensten von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Der Bereitstellungsprozess für die Lync-Skype-Konnektivität wurde im Vergleich zu früheren PIC-Bereitstellungsmethoden geändert. Bei diesem Bereitstellungsprozess kann es bis zu 30 Tage dauern, bis der Prozess abgeschlossen ist. Wir empfehlen, diesen Prozess zuerst zu starten, bevor Sie die verbleibenden Schritte in diesem Dokument ausführen. Nachdem der Lync-Skype-Bereitstellungsprozess für Ihr Konto abgeschlossen wurde, wird das Konto aktiviert und den entsprechend berechtigten Benutzern wird die Verbindung zu öffentlichen Instant Messaging-Anbietern ermöglicht.

### Für die Bereitstellung der Lync-Skype-Konnektivität benötigen Sie die folgenden Informationen:

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
<tr class="even">
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


### So starten Sie den Bereitstellungsprozess für die Lync-Skype-Konnektivität:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Melden Sie sich mit Ihrer Microsoft Windows Live-ID bei der Website <strong>https://pic.lync.com</strong> an.</p></li>
<li><p>Wählen Sie den Typ Ihres Microsoft-Lizenzvertrags aus.</p></li>
<li><p>Aktivieren Sie das Kontrollkästchen, um zu bestätigen, dass Sie die Produktbenutzungsrechte für Lync Server gelesen haben und akzeptieren.</p></li>
<li><p>Klicken Sie auf der Seite <strong>Initiate a Provisioning Request</strong> (Bereitstellungsprozess starten) auf den entsprechenden Link zum Starten eines Bereitstellungsprozesses.</p></li>
<li><p>Geben Sie auf der Seite <strong>Specify Provisioning Information</strong> (Bereitstellungsinformationen angeben) den <strong>FQDN des Zugriffs-Edgediensts</strong> an, z. B. <strong>accessedge.contoso.com</strong>.</p></li>
<li><p>Geben Sie mindestens einen SIP-Domänennamen ein und klicken Sie auf <strong>Hinzufügen</strong>.</p>
<div>

> [!IMPORTANT]
> Es sind mindestens ein Zugriffs-Edgeserver und eine SIP-Domäne erforderlich, um den Bereitstellungsprozess abzuschließen. Die SIP-Domäne und der Zugriffs-Edgeserver müssen aktiv sein, funktionieren und im Netzwerk erreichbar sein.


</div></li>
<li><p>Wählen Sie in der Liste der <strong>öffentlichen Anbieter von Chatdiensten</strong> den Eintrag <strong>Skype</strong> aus und klicken Sie auf <strong>Weiter</strong>, um Kontaktinformationen hinzuzufügen. Senden Sie anschließend die Bereitstellungsanforderung.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><ol>
<li><p>Melden Sie sich mit Ihrer Microsoft Windows Live-ID bei der Website <strong>https://pic.lync.com</strong> an.</p></li>
<li><p>Wählen Sie den Typ Ihres Microsoft-Lizenzvertrags aus.</p></li>
<li><p>Aktivieren Sie das Kontrollkästchen, um zu bestätigen, dass Sie die Produktbenutzungsrechte für Lync Server gelesen haben und akzeptieren.</p></li>
<li><p>Klicken Sie auf der Seite <strong>Initiate a Provisioning Request</strong> (Bereitstellungsprozess starten) auf den entsprechenden Link zum Starten eines Bereitstellungsprozesses.</p></li>
<li><p>Geben Sie auf der Seite <strong>Specify Provisioning Information</strong> (Bereitstellungsinformationen angeben) den <strong>FQDN des Zugriffs-Edgediensts</strong> an, z. B. <strong>accessedge.contoso.com</strong>.</p></li>
<li><p>Geben Sie mindestens einen SIP-Domänennamen ein und klicken Sie auf <strong>Hinzufügen</strong>.</p>
<div>

> [!IMPORTANT]
> Es sind mindestens ein Zugriffs-Edgeserver und eine SIP-Domäne erforderlich, um den Bereitstellungsprozess abzuschließen. Die SIP-Domäne und der Zugriffs-Edgeserver müssen aktiv sein, funktionieren und im Netzwerk erreichbar sein.


</div></li>
<li><p>Wählen Sie in der Liste der <strong>öffentlichen Anbieter von Chatdiensten</strong> den Eintrag <strong>Skype</strong> aus und klicken Sie auf <strong>Weiter</strong>, um Kontaktinformationen hinzuzufügen. Senden Sie anschließend die Bereitstellungsanforderung.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Nachdem die Bereitstellungsanforderung gesendet wurde, kann es bis zu 30 Tage dauern, bis das Konto aktiviert und den Benutzern die Verbindung zu öffentlichen Instant Messaging-Anbietern ermöglicht wird.

## Aktivieren von Partnerverbunden und Verbindungen mit öffentlichen Instant Messaging-Diensten (PIC)

Nachdem Sie die Bereitstellungsanforderung übermittelt haben, können Sie sich auf die Lync Server-Umgebung und die Verwaltungsaufgaben konzentrieren, die für die Konfiguration der Lync-Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Lync Server-Administrator Lync Lync Server schon bereitstellt und den externen Zugriff konfiguriert hat. Weitere Informationen zum Konfigurieren des externen Zugriffs für Lync Server finden Sie unter "Planen des Zugriffs externer Benutzer" an [http://go.microsoft.com/fwlink/p/?LinkID=273772](http://go.microsoft.com/fwlink/p/?linkid=273772) und unter "Bereitstellen des Zugriffs für externe Benutzer" an [http://go.microsoft.com/fwlink/p/?LinkID=27378](http://go.microsoft.com/fwlink/p/?linkid=27378).

Zur Vorbereitung der Lync Server-Umgebung für die Lync-Skype-Konnektivität muss der Lync Server-Administrator die folgenden drei Aufgaben erfüllen:

## 1\. Konfigurieren des Partnerverbunds und der PIC

Der Partnerverbund ist erforderlich, damit Skype-Benutzer mit Lync-Benutzern in Ihrer Organisation kommunizieren können. PIC (Public Instant Messaging Connectivity, Verbindung mit öffentlichen Instant Messaging-Diensten) ist eine Partnerverbundklasse und muss konfiguriert werden, damit Lync-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mit der Lync Server-Systemsteuerung konfiguriert, die nachstehend abgebildet ist.


> [!IMPORTANT]
> Der PIC-Partnerverbund wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt. Zu den unterstützen Plattformen für den PIC-Partnerverbund gehören Lync Server 2013, Lync Server 2010 und Office Communications Server 2007 R2.



## 2\. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund

Der Administrator muss in der Lync Server-Systemsteuerung mindestens eine Richtlinie für den Zugriff externer Benutzer konfigurieren, um zu steuern, ob Skype-Benutzer mit internen Lync Server-Benutzern zusammenarbeiten können.

## 3\. Konfigurieren der Einstellung des Skype PIC-Anbieters für Lync

Der Administrator muss in der Lync Server-Verwaltungsshell die Lync-Clientrichtlinie so konfigurieren, dass Skype als weiterer PIC-Anbieter angezeigt wird.


> [!NOTE]
> Benutzer von PIC-Dienstanbietern können erst dann an Chatunterhaltungen oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie zudem mindestens eine Richtlinie (Schritt 2 an früher Stelle in diesem Verfahren) zur Unterstützung der Verbindung zu öffentlichen Instant Messaging-Anbietern konfiguriert haben.<BR>Informationen zum Konfigurieren des Partnerverbunds und von PIC finden Sie unter "Aktivieren oder Deaktivieren des Partnerverbunds und der Anbindung an öffentliche Instant Messaging-Dienste" an <A href="http://go.microsoft.com/fwlink/p/?linkid=306063">http://go.microsoft.com/fwlink/p/?LinkId=306063</A>.<BR>Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund finden Sie unter "Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs" an <A href="http://go.microsoft.com/fwlink/p/?linkid=306064">http://go.microsoft.com/fwlink/p/?LinkId=306064</A>.



1.  Öffnen Sie auf einem Lync Server-Front-End-Server die Lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden beiden Befehle aus:
    
      - Remove-CsPublicProvider -Identity Messenger
    
      - New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger\_16x16.png" -VerificationLevel 2 -Enabled 1

3.  Auf einem Lync-Client können Sie jetzt Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie dessen Microsoft-Konto angeben. Darüber hinaus kann ein Skype-Benutzer, der sein Microsoft-Konto zusammengeführt hat und bei diesem angemeldet ist, Kontaktanfragen an Lync-Benutzer senden. Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/de/faq/fa12059/what-is-a-microsoft-account). Weitere Informationen zum Hinzufügen von Kunden zu Lync finden Sie unter [Verwenden von Lync-Skype-Konnektivität als Endbenutzer in Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Detaillierte Informationen zum Ändern von gehosteten Anbietern finden Sie unter "Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern" an [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).

Damit sind die Verwaltungsaufgaben abgeschlossen, die auf dem Server durchgeführt werden müssen, und die Lync-Skype-Konnektivität ist eingerichtet.

## Weitere Ressourcen

[Verwenden von Lync-Skype-Konnektivität als Endbenutzer in Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Provisioning guide for Lync-Skype connectivity in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)


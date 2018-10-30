---
title: 'Lync Server 2013: Aktivieren der Lync-Skype-Konnektivität'
TOCTitle: Aktivieren der Lync-Skype-Konnektivität
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn440170(v=OCS.15)
ms:contentKeyID: 59373617
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Lync-Skype-Konnektivität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Nachdem Sie die Bereitstellungsanforderung übermittelt haben, können Sie sich auf die Lync Server-Umgebung und die Verwaltungsaufgaben konzentrieren, die für die Konfiguration der Lync-Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Lync Server-Administrator Lync Lync Server schon bereitstellt und den externen Zugriff konfiguriert hat. Weitere Informationen zum Konfigurieren des externen Zugriffs für Lync Server finden Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Zur Vorbereitung der Lync Server-Umgebung für die Lync-Skype-Konnektivität muss der Lync Server-Administrator die folgenden drei Aufgaben erfüllen:

## 1\. Konfigurieren des Partnerverbunds und der PIC

Der Partnerverbund ist erforderlich, damit Skype-Benutzer mit Lync-Benutzern in Ihrer Organisation kommunizieren können. PIC (Public Instant Messaging Connectivity, Verbindung mit öffentlichen Instant Messaging-Diensten) ist eine Partnerverbundklasse und muss konfiguriert werden, damit Lync-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mit der Lync Server-Systemsteuerung konfiguriert, die nachstehend abgebildet ist.

![Anzeigen von PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Anzeigen von PIC")


> [!IMPORTANT]
> Der PIC-Partnerverbund wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt. Zu den unterstützen Plattformen für den PIC-Partnerverbund gehören Lync Server 2013, Lync Server 2010 und Office Communications Server 2007 R2.



## 2\. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund

Der Administrator muss in der Lync Server-Systemsteuerung mindestens eine Richtlinie für den Zugriff externer Benutzer konfigurieren, um zu steuern, ob Skype-Benutzer mit internen Lync Server-Benutzern zusammenarbeiten können.

![Richtlinien](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Richtlinien")

## 3\. Konfigurieren der Einstellung des Skype PIC-Anbieters für Lync

Der Administrator muss in der Lync Server-Verwaltungsshell die Lync-Clientrichtlinie so konfigurieren, dass Skype als weiterer PIC-Anbieter angezeigt wird.


> [!NOTE]
> Benutzer von PIC-Dienstanbietern können erst dann an Chats oder Audio- oder Videokonferenzen in Ihrer Organisation teilnehmen, wenn Sie zudem mindestens eine Richtlinie (Schritt 2 an früherer Stelle in diesem Verfahren) zur Unterstützung der Verbindung zu öffentlichen Chatanbietern konfiguriert haben.



1.  Informationen zum Konfigurieren des Partnerverbunds und von PIC finden Sie unter "Aktivieren oder Deaktivieren des Partnerverbunds und der Anbindung an öffentliche Instant Messaging-Dienste" an [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).

2.  Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund finden Sie unter "Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs" an [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).

**So bearbeiten Sie einen Messenger PIC-Anbieter und konfigurieren ihn für Skype**

1.  Öffnen Sie auf einem Lync Server-Front-End-Server die Lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden beiden Befehle aus:
    
    `Remove-CsPublicProvider -Identity Messenger`
    
    `New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png" -VerificationLevel 2 -Enabled 1`

3.  Auf einem Lync-Client können Sie jetzt Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie dessen Microsoft-Konto angeben. Darüber hinaus kann ein Skype-Benutzer, der sein Microsoft-Konto zusammengeführt hat und bei diesem angemeldet ist, Kontaktanfragen an Lync-Benutzer senden. Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/de/faq/fa12059/what-is-a-microsoft-account). Weitere Informationen zum Hinzufügen von Kunden zu Lync finden Sie unter [Verwenden von Lync-Skype-Konnektivität als Endbenutzer in Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Hinzufügen eines Skype-Kontakts](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Hinzufügen eines Skype-Kontakts")

4.  Detaillierte Informationen zum Ändern von gehosteten Anbietern finden Sie unter "Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern" an [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).

Damit sind die Verwaltungsaufgaben abgeschlossen, die auf dem Server durchgeführt werden müssen, und die Lync-Skype-Konnektivität ist eingerichtet.


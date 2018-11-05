---
title: 'Lync Server 2013: Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration'
TOCTitle: Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413088(v=OCS.15)
ms:contentKeyID: 49296025
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-08-07_

Wenn Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie zum Überprüfen, Veröffentlichen oder Verwerfen der ausstehenden Änderungen die folgenden Schritte aus.


> [!IMPORTANT]
> Stellen Sie sicher, dass jeweils nur ein Benutzer Änderungen an den Konfigurationseinstellungen für das VoIP-Routing vornimmt.<BR>Alle ausstehenden Änderungen müssen gleichzeitig über den Befehl <STRONG>Commit für alle</STRONG> veröffentlicht werden. Es ist nicht möglich, nur ausgewählte ausstehende Änderungen zu veröffentlichen. Führen Sie den Befehl <STRONG>Nicht übernommene Änderungen überprüfen</STRONG> aus, bevor Sie ausstehende Änderungen veröffentlichen, und verwerfen Sie Konfigurationsänderungen, die nicht veröffentlicht werden sollen.<BR>Wenn Sie die Seiten in der Gruppe <STRONG>VoIP-Routing</STRONG> verlassen, bevor Sie für ausstehende Änderungen ein Commit ausführen, gehen alle ausstehenden Änderungen verloren. Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine VoIP-Konfigurationsdatei exportieren und die aktualisierte Konfiguration anschließend importieren und veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Exportieren einer VoIP-Routenkonfigurationsdatei in Lync Server 2013</A>.



## So überprüfen, veröffentlichen oder verwerfen Sie Konfigurationsänderungen für das VoIP-Routing

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** .

4.  Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf den einzelnen Seiten der Gruppe **VoIP-Routing** vor.

5.  Wählen Sie im Menü **Commit** die Option **Nicht übernommene Änderungen überprüfen** , um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen.

6.  Führen Sie eine der folgenden Aktionen aus, um ausstehende Änderungen zu verwerfen:
    
      - Wählen Sie im Menü **Commit** die Option **Alle nicht übernommenen Änderungen verwerfen** .
    
      - Wechseln Sie auf der Seite **VoIP-Routing** zur Registerkarte mit ausstehenden Änderungen, die verworfen werden sollen, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit** , und klicken Sie dann auf **Ausgewählte Änderungen verwerfen** .

7.  Nachdem Sie alle ausstehenden Änderungen überprüft und die Änderungen verworfen haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit** und dann auf **Commit für alle** .

8.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen ohne Commit** , das eine Liste aller ausstehenden Änderungen enthält, auf **OK** .
    
    Wenn die Änderungen in der Lync Server-Systemsteuerung übernommen wurden, wird die Meldung **VoIP-Routingkonfiguration erfolgreich veröffentlicht** angezeigt.


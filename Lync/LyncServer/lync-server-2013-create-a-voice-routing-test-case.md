---
title: 'Lync Server 2013: Erstellen eines Testfalls für das VoIP-Routing'
TOCTitle: Erstellen eines Testfalls für das VoIP-Routing
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425935(v=OCS.15)
ms:contentKeyID: 49293837
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen eines Testfalls für das VoIP-Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

## So erstellen Sie einen Testfall

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen** .

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **Neu** , um einen neuen Testfall zu erstellen.

5.  Geben Sie unter **Name** einen eindeutigen Namen für den Testfall ein.
    
    Der Name muss unter allen VoIP-Routing-Testfällen in Ihrer Enterprise-VoIP-Bereitstellung eindeutig sein. Er kann bis zu 32 Zeichen lang sein und beliebige alphanumerische Zeichen sowie umgekehrte Schrägstriche (\\), Punkte (.) oder Unterstriche (\_) enthalten.

6.  Geben Sie unter **Zu testende gewählte Rufnummer** die gewählte Rufnummer ein, die Sie zum Testen der für diesen Testfall angegebenen Routingkonfiguration verwenden möchten. Basierend auf dem Satz mit Wähleinstellungen, der Route und der VoIP-Richtlinie wird diese Nummer normalisiert und als Ausgabe angezeigt.

7.  Wählen Sie in der Liste **Wähleinstellungen** den Satz mit Wähleinstellungen aus, der bei Ausführung des Tests verwendet werden soll. Standardeinstellung ist der globale Satz mit Wähleinstellungen.

8.  Wählen Sie in der Liste **VoIP-Richtlinie** die VoIP-Richtlinie aus, die bei Ausführung des Tests verwendet werden soll. Standardeinstellung ist die globale VoIP-Richtlinie.

9.  Geben Sie unter **Erwartete Übersetzung** die Telefonnummer in dem Format ein, in dem sie nach der Übersetzung vorliegen soll. Hierbei handelt es sich um den Wert der getesteten Telefonnummer, nachdem diese durch die erste den Kriterien entsprechende Normalisierungsregel in den ausgewählten Wähleinstellungen übersetzt wurde. Wenn die getestete Nummer bei Ausführung des Testfalls nicht den Wert in **Erwartete Übersetzung** ergibt, ist der Test nicht erfolgreich.

10. (Optional) In der Liste **Erwartete PSTN-Verwendung** können Sie basierend auf den ausgewählten Wähleinstellungen und der VoIP-Richtlinie den PSTN-Verwendungsdatensatz (Public Switched Telephone Network, Telefonfestnetz) auswählen, der beim Ausführen des Testfalls verwendet werden soll. Wird ein anderer PSTN-Verwendungsdatensatz verwendet, ist der Test nicht erfolgreich.

11. (Optional) In der Liste **Erwartete Route** können Sie basierend auf den ausgewählten Wähleinstellungen und der VoIP-Richtlinie die VoIP-Route auswählen, die beim Ausführen des Testfalls verwendet werden soll. Wird eine andere VoIP-Route verwendet, ist der Test nicht erfolgreich.

12. (Optional) Klicken Sie auf **Ausführen** , um den Testfall auszuführen. Die Ergebnisse werden im rechten Seitenbereich angezeigt.

13. Klicken Sie auf **OK** .

14. Klicken Sie auf **Commit** und anschließend auf **Commit für alle** .
    

    > [!NOTE]
    > Jedes Mal, wenn Sie einen Testplan für das VoIP-Routing erstellen, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A> in der Betriebsdokumentation.

    
    Wenn der im Test verwendete Satz mit Wähleinstellungen Telefonnummern normalisiert, die mit einem Pluszeichen beginnen (z. B. +12065551219), führt dieser Satz möglicherweise dazu, dass der Test für das VoIP-Routing fehlschlägt. (Der Satz mit Wähleinstellungen und die VoIP-Route funktionieren, tatsächlich wird Test-CsDialPlan erfolgreich abgeschlossen. Aber das VoIP-Routing schlägt möglicherweise fehl.) Das ist etwas, das Sie beim Testen von VoIP-Routen bedenken sollten.

## Siehe auch

#### Aufgaben

[Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  

#### Weitere Ressourcen

[Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)


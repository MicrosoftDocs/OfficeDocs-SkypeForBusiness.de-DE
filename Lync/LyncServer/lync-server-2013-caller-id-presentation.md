---
title: 'Lync Server 2013: Darstellung der Anrufer-ID'
TOCTitle: Darstellung der Anrufer-ID
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204980(v=OCS.15)
ms:contentKeyID: 49294295
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Darstellung der Anrufer-ID in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Mit Lync Server 2010 kann die Telefonnummer des angerufenen Teilnehmers (d. h., die gewählte Telefonnummer) vom E.164-Format in das für den *Trunkpeer* (also das zugeordnete Gateway, Nebenstellensystem oder der zugeordnete SIP-Trunk) erforderliche lokale Wählformat übersetzt werden. Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.

Neu in Lync Server 2013 ist die Möglichkeit, auch die Telefonnummer des Anrufers (d. h. die Telefonnummer, von der der Anrufer aus anruft) aus dem E.164-Format in das vom Trunk-Peer benötigte lokale Wählformat zu übersetzen. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe "+44" am Beginn einer Wählzeichenfolge entfernt und durch "0144" ersetzt.

**So konfigurieren Sie die Anrufer-ID in der Lync Server-Systemsteuerung**

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration** .

4.  Doppelklicken Sie auf der Seite **Trunkkonfiguration** auf einen vorhandenen Trunk (z. B. auf den Trunk **Global** ), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.

5.  So konfigurieren Sie die Rufnummernanzeige:
    
      - Klicken Sie zur Auswahl einer oder mehrerer Regeln aus der Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren Übersetzungsregeln auf **Auswählen** . Klicken Sie in **Übersetzungsregeln für Anrufernummern** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK** .
    
      - Klicken Sie auf **Neu** , um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen** , um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.
    
      - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen** . Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen** .
    

    > [!WARNING]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.



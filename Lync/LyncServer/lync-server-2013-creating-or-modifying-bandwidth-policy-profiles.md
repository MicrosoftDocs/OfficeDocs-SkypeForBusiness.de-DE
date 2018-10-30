---
title: Erstellen oder Ändern von Bandbreitenrichtlinienprofilen
TOCTitle: Erstellen oder Ändern von Bandbreitenrichtlinienprofilen
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520945(v=OCS.15)
ms:contentKeyID: 49293097
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern von Bandbreitenrichtlinienprofilen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Microsoft Lync Server 2013 können Bandbreiteneinschränkungen nur für Audio und Video zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Mithilfe der Lync Server-Systemsteuerung können Sie ein Containerprofil für diese Richtlinien erstellen, ändern oder löschen. Jedes Bandbreitenrichtlinienprofil kann mindestens einem Netzwerkstandort zugeordnet werden. Erstellen oder ändern Sie mithilfe der folgenden Verfahren ein Bandbreitenrichtlinienprofil. Informationen zum Löschen eines Bandbreitenrichtlinienprofils finden Sie unter [Löschen von Netzwerk-Bandbreitenrichtlinienprofilen](lync-server-2013-deleting-network-bandwidth-policy-profiles.md).

## So erstellen Sie ein neues Bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf **Neu**.

5.  Geben Sie im Abschnitt **Neues Bandbreitenrichtlinienprofil** im Feld **Name** einen Namen ein. Dieser Name muss eindeutig sein.

6.  Geben Sie im Feld **Audiolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Audioverbindungen in KBit/s fest.

7.  Geben Sie im Feld **Audiositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Audioverbindung in KBit/s fest. Dieser Wert muss auf mindestens 40 festgelegt werden.

8.  Geben Sie im Feld **Videolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Videoverbindungen in KBit/s fest.

9.  Geben Sie im Feld **Videositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Videoverbindung in KBit/s fest. Dieser Wert muss auf mindestens 100 festgelegt werden.

10. (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Bandbreitenrichtlinienprofil ein, die nicht durch den Namen allein vermittelt werden können.

11. Klicken Sie auf **Commit**.
    

    > [!NOTE]
    > Beim Erstellen eines neuen Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen nicht automatisch erzwungen. Sie müssen das Richtlinienprofil zunächst einem Standort zuordnen. Ausführliche Informationen zum Zuordnen eines Richtlinienprofils zu einem Standort finden Sie unter <A href="lync-server-2013-creating-or-modifying-network-sites.md">Erstellen oder Ändern von Netzwerkstandorten</A>.



## So ändern Sie ein Bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Bandbreitenrichtlinienprofil, das Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **Bandbreitenrichtlinienprofil bearbeiten** die gewünschten Felder (ausführliche Informationen finden Sie im Abschnitt "So erstellen Sie ein neues Bandbreitenrichtlinienprofil" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit**.
    

    > [!NOTE]
    > Beim Ändern des Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen aller Netzwerkstandorte, die diesem Bandbreitenrichtlinienprofil zugeordnet sind, umgehend aktualisiert.



## Siehe auch

#### Aufgaben

[Löschen von Netzwerk-Bandbreitenrichtlinienprofilen](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### Weitere Ressourcen

[Konfigurieren der Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)


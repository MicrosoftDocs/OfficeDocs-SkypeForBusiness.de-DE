---
title: Löschen von Netzwerk-Bandbreitenrichtlinienprofilen
TOCTitle: Löschen von Netzwerk-Bandbreitenrichtlinienprofilen
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49890741
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von Netzwerk-Bandbreitenrichtlinienprofilen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Bandbreitenrichtlinien werden im Rahmen der Anrufsteuerung eingesetzt, um die Bandbreitenbeschränkungen für bestimmte Modalitäten festzulegen. In Microsoft Lync Server 2013 können nur Audio- und Videomodalitäten Bandbreiteneinschränkungen zugewiesen werden. Bandbreiteneinschränkungen können global oder für einzelne Sitzungen zugewiesen werden. Mit Lync Server-Systemsteuerung können Sie ein Containerprofil für diese Richtlinien erstellen, bearbeiten und löschen. Mit den folgenden Verfahren können Sie Richtlinienprofile für Netzwerkbandbreiten löschen. Nähere Informationen zum Erstellen oder Bearbeiten von Richtlinienprofilen für Netzwerkbandbreiten finden Sie unter [Erstellen oder Ändern von Bandbreitenrichtlinienprofilen](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

## So löschen Sie ein Richtlinienprofil für die Bandbreite

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Richtlinienprofil der Bandbreite, das Sie löschen möchten.
    

    > [!NOTE]
    > Sie können auch mehrere Profile auf einmal löschen. Drücken Sie dazu die STRG-TASTE, und halten Sie sie gedrückt, während Sie mit der Maus auf die einzelnen Profile klicken. Wenn Sie alle Profile auswählen möchten, klicken Sie einfach im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Abschließend klicken Sie im Menü **Bearbeiten** auf **Löschen**.
    

    > [!WARNING]
    > Richtlinienprofile für Bandbreiten, die mit einem Netzwerkstandort verknüpft sind, können nicht ohne Weiteres gelöscht werden. In diesem Fall müssen Sie zuerst die Verknüpfung mit dem Netzwerkstandort aufheben, bevor Sie das Profil löschen können. Nähere Informationen zum Bearbeiten des Netzwerkstandorts finden Sie unter <A href="lync-server-2013-creating-or-modifying-network-sites.md">Erstellen oder Ändern von Netzwerkstandorten</A>.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Bandbreitenrichtlinienprofilen](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Anzeigen von Informationen zu Netzwerk-Bandbreitenrichtlinienprofilen](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  

#### Weitere Ressourcen

[Konfigurieren der Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)


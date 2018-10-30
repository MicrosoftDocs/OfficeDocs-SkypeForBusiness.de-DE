---
title: Anzeigen von Informationen zu Netzwerk-Bandbreitenrichtlinienprofilen
TOCTitle: Anzeigen von Informationen zu Netzwerk-Bandbreitenrichtlinienprofilen
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49891005
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Netzwerk-Bandbreitenrichtlinienprofilen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Microsoft Lync Server 2013 können Bandbreiteneinschränkungen nur für Audio und Video zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Mithilfe der Lync Server-Systemsteuerung können Sie ein Containerprofil für diese Richtlinien erstellen, ändern oder löschen. Jedes Bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet werden. Verwenden Sie die folgenden Verfahren, um ein Bandbreitenrichtlinienprofil anzuzeigen. Informationen zum Erstellen oder Ändern eines Bandbreitenrichtlinienprofils finden Sie unter [Erstellen oder Ändern von Bandbreitenrichtlinienprofilen](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

## So ändern Sie ein Bandbreitenrichtlinienprofil

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Bandbreitenrichtlinienprofil, das geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

## Anzeigen von Profilinformationen für Netzwerkbandbreitenrichtlinien mithilfe von Lync Server PowerShell-Cmdlets

Sie können Netzwerkbandbreitenprofile auch mithilfe von Lync Server PowerShell und des **Get-CsNetworkBandwidthPolicyProfile**-Cmdlets anzeigen. Dieses Cmdlet können Sie entweder in der Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell.

## Anzeigen von Informationen zu Netzwerk-Bandbreitenrichtlinienprofilen

  - Zum Anzeigen von Informationen zu allen Netzwerk-Bandbreitenrichtlinienprofilen geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein und drücken dann die EINGABETASTE:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

Weitere Informationen finden Sie in dem Hilfethema zum [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)-Cmdlet.

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Bandbreitenrichtlinienprofilen](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Löschen von Netzwerk-Bandbreitenrichtlinienprofilen](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### Weitere Ressourcen

[Konfigurieren der Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)


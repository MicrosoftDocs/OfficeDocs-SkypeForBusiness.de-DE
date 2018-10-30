---
title: Anzeigen von Informationen zu Netzwerkschnittstellen
TOCTitle: Anzeigen von Informationen zu Netzwerkschnittstellen
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49890983
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Netzwerkschnittstellen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

## Anzeigen von Netzwerkschnittstelleninformationen mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Netzwerkschnittstelleninformationen können Sie mit der Lync Server-Verwaltungsshell und dem **Get-CsNetworkInterface**-Cmdlet anzeigen. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Netzwerkschnittstelleninformationen an

  - Um Netzwerkschnittstelleninformationen anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkInterface
    
    Mit dem folgenden Befehl werden für jede Netzwerkschnittstelle Informationen, die so oder ähnlich aussehen, zurückgegeben:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :

Ausführliche Informationen dazu finden Sie unter [Get-CsNetworkInterface](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterface).


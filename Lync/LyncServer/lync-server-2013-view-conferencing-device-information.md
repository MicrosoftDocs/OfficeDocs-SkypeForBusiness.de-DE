---
title: Anzeigen von Informationen zu Konferenzgeräten
TOCTitle: Anzeigen von Informationen zu Konferenzgeräten
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994043(v=OCS.15)
ms:contentKeyID: 52056394
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Konferenzgeräten

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Mit dem Cmdlets Windows PowerShell und **Get-CsMeetingRoom** können Sie Informationen zu den Konferenzgeräten abrufen, die für die Verwendung in Ihrer Organisation konfiguriert sind. Führen Sie das Cmdlet **Get-CsMeetingRoom** entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell aus.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



Wenn Sie das Cmdlet **Get-CsMeetingRoom** ohne Parameter anwenden, werden Informationen zu allen Ihren Konferenzgeräten zurückgegeben. Optionale Parameter bieten verschiedene Möglichkeiten zum Filtern von Informationen. Ausführliche Informationen finden Sie im Abschnitt zu Parametern unter [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).


## Anzeigen von Informationen zu allen Ihren Konferenzgeräten

  - Zum Anzeigen von Details zu allen Ihren Konferenzgeräten geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein und drücken dann die EINGABETASTE:
    
        Get-CsMeetingRoom
    
    Mit diesem Cmdlet werden Informationen zu den einzelnen Konferenzgeräten nach folgendem Muster zurückgegeben. Dieses Beispiel zeigt nur einen Teil der Informationen, die beim Ausführen dieses Cmdlets zurückgegeben werden:
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

## Anzeigen von Informationen zu einem bestimmten Konferenzgerät

  - Zum Anzeigen von Informationen zu einem bestimmten Konferenzgerät geben Sie den Identity-Parameter gefolgt von der Identität des Konferenzgeräts an (in der Regel der Active Directory-Anzeigename). Beispiel:
    
        Get-CsMeetingRoom -Identity "Room 1219"

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).


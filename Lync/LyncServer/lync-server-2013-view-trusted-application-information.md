---
title: Anzeigen von Informationen zu vertrauenswürdigen Anwendungen
TOCTitle: Anzeigen von Informationen zu vertrauenswürdigen Anwendungen
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49890805
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu vertrauenswürdigen Anwendungen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-30_

Verwenden Sie die folgende Vorgehensweise, um Informationen von vertrauenswürdigen Verwaltungsshell für Lync Server 2013-Anwendungen in Lync Server-Verwaltungsshell anzuzeigen.

## Anzeigen von Informationen zu vertrauenswürdigen Anwendungen mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Sie können Informationen zu Ihren vertrauenswürdigen Anwendungen mithilfe von Lync Server-Verwaltungsshell und dem **Get-CsTrustedApplication**-Cmdlet anzeigen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie vertrauenswürdige Anwendungen an

  - Sie können alle Ihre vertrauenswürdigen Anwendungen anzeigen, indem Sie in der Lync Server-Verwaltungsshell den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Get-CsConferenceDisclaimer
    
    Mit diesem Befehl werden Informationen zu den einzelnen vertrauenswürdigen Anwendungen nach folgendem Muster zurückgegeben:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True

Ausführliche Informationen finden Sie unter [Get-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrustedApplication).


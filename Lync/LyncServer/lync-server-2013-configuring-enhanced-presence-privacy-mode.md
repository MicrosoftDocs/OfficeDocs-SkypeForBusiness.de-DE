---
title: 'Lync Server 2013: Konfigurieren des Datenschutzmodus für erhöhte Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Konfigurieren des erweiterten Anwesenheitsdaten Schutzmodus in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-08_

Mit dem erweiterten Anwesenheitsdaten Schutzmodus können Benutzer ihre Anwesenheitsinformationen so einschränken, dass Sie nur für die Kontakte sichtbar sind, die in ihrer lync 2013-Kontaktliste aufgeführt sind. Die Cmdlets **New-CsPrivacyConfiguration** und **CsPrivacyConfiguration** verfügen über einen EnablePrivacyMode-Parameter, der diese Option steuert. Wenn EnablePrivacyMode auf "true" festgelegt ist, wird die Option zum Einschränken der Anwesenheitsinformationen auf Kontakte in den lync 2013-Status Optionen zur Verfügung gestellt. Wenn EnablePrivacyMode auf "false" festgelegt ist, können Benutzer entweder immer zulassen, dass ihre Anwesenheitsinformationen angezeigt werden, oder alle zukünftigen Änderungen einhalten, die der Administrator am Datenschutzmodus vornimmt.

<div>


> [!IMPORTANT]  
> Die Privatsphäre-Einstellungen von lync 2013 und lync 2010 werden von früheren Versionen (Microsoft Office Communicator 2007 R2 oder Microsoft Office Communicator 2007) nicht berücksichtigt. Wenn frühere Versionen von Office Communicator angemeldet werden können, kann ein lync 2013-Benutzerstatus, die Kontaktinformationen oder das Bild von einer Person angezeigt werden, die nicht autorisiert ist, Sie anzuzeigen. Darüber hinaus werden die Privatsphäre-Einstellungen eines lync 2013-Benutzers zurückgesetzt, wenn er sich später mit der vorherigen Version von Communicator anmeldet.<BR>Aus diesen Gründen in einem Migrationsszenario, bevor Sie den erweiterten Anwesenheitsdaten Schutzmodus aktivieren: 
> <UL>
> <LI>
> <P>Stellen Sie sicher, dass auf jedem Benutzer lync 2013 installiert ist.</P>
> <LI>
> <P>Definieren Sie eine clientversionsrichtlinien Regel, um zu verhindern, dass frühere Versionen von Communicator angemeldet werden.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>So aktivieren Sie den Datenschutzmodus für erhöhte Anwesenheit

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie den folgenden Befehl aus:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Dieser Befehl aktiviert den Datenschutzmodus für alle Datenschutz-Konfigurationseinstellungen, die derzeit in der Organisation verwendet werden. Weitere Informationen dazu, wie die Richtlinienkonfigurationen für den lync Server Enhanced Presence-Datenschutzmodus die Kontakt Anwesenheit für den lync 2013-Client verwalten, finden Sie im Microsoft Knowledge Base-Artikel [Aktivieren des Datenschutzmodus für erweiterte Anwesenheitsinformationen in lync Server für die Anwesenheit Status einiger lync-Kontakte "nicht verfügbar"](http://support.microsoft.com/kb/3020057)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[Neu – CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Satz-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


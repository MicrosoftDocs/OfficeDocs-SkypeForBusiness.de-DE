---
title: 'Lync Server 2013: Konfigurieren des Datenschutzmodus für erweiterte Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a06a7bf01664c260ace3a86537665e185b64f8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532602"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Konfigurieren des Datenschutzmodus für erweiterte Anwesenheitsinformationen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-08_

Mit dem Datenschutzmodus für erweiterte Anwesenheit können Benutzer ihre Anwesenheitsinformationen so einschränken, dass Sie nur für die Kontakte sichtbar sind, die in ihrer lync 2013 Kontaktliste aufgeführt sind. Die Cmdlets **New-CsPrivacyConfiguration**   und **Sets-CsPrivacyConfiguration** verfügen über einen EnablePrivacyMode-Parameter, der diese Option steuert. Wenn EnablePrivacyMode auf "true" festgelegt ist, wird die Option zum Einschränken der Anwesenheitsinformationen auf Kontakte in den lync 2013 Status Optionen verfügbar. Wenn EnablePrivacyMode auf "false" festgelegt ist, können Benutzer auswählen, dass jeder immer seine Anwesenheitsinformationen anzeigen oder sich an zukünftige Änderungen halten kann, die der Administrator im Datenschutzmodus durchführt.

<div>


> [!IMPORTANT]  
> Lync 2013-und lync 2010-Datenschutzeinstellungen werden durch frühere Versionen (Microsoft Office Communicator 2007 R2 oder Microsoft Office Communicator 2007) nicht berücksichtigt. Wenn sich frühere Versionen von Office Communicator anmelden können, kann der Status eines lync 2013 Benutzers, die Kontaktinformationen oder das Bild von einer Person angezeigt werden, die nicht berechtigt ist, Sie anzuzeigen. Darüber hinaus werden die Datenschutzeinstellungen eines lync 2013 Benutzers zurückgesetzt, wenn er sich später mit einer früheren Version von Communicator anmeldet.<BR>Aus diesen Gründen in einem Migrationsszenario, bevor Sie den erweiterten Datenschutzmodus für Anwesenheit aktivieren: 
> <UL>
> <LI>
> <P>Stellen Sie sicher, dass alle Benutzer lync 2013 installiert haben.</P>
> <LI>
> <P>Definieren Sie eine clientversionsrichtlinien Regel, um zu verhindern, dass sich frühere Versionen von Communicator anmelden.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>So aktivieren Sie den Datenschutzmodus für erweiterte Anwesenheit

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie den folgenden Befehl aus:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Mit diesem Befehl wird der Datenschutzmodus für alle derzeit in der Organisation verwendeten Datenschutz-Konfigurationseinstellungen aktiviert. Weitere Informationen darüber, wie die Richtlinienkonfigurationen für den lync Server Enhanced Presence-Datenschutzmodus die Kontakt Anwesenheit für den lync 2013-Client verwaltet, finden Sie im Microsoft KB-Artikel [aktivieren lync Server erweiterten Anwesenheitsdaten Modus aktualisiert den Anwesenheitsstatus einiger lync-Kontakte auf "nicht verfügbar"](https://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Gruppe-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


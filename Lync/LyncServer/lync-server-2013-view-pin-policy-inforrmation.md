---
title: 'Lync Server 2013: PIN-Richtlinie anzeigen Linien'
description: 'Lync Server 2013: View Pin Policy Linien.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d60125663bed2b79921de62663865c56b6a27786
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579641"
---
# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>PIN-Richtlinie Linien in lync Server 2013 anzeigen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Sie können die Registerkarte **PIN-Richtlinie** verwenden, um die PIN-Authentifizierung (Personal Identification Number) von Benutzern anzuzeigen, die eine Verbindung mit lync 2013 mit IP-Telefonen herstellen. Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist. Ausführliche Informationen finden Sie unter [Ändern vorhandener Webdienst-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu ändern.

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>So zeigen Sie Informationen zu einer PIN-Richtlinie in lync Server-Systemsteuerung an

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.

4.  Klicken Sie auf der Seite **PIN-Richtlinie** auf eine Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Anzeigen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können auch PIN-Richtlinien anzeigen, indem Sie Windows PowerShell und das Get-CsPinPolicy-Cmdlet verwenden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-pin-policies"></a>So zeigen Sie PIN-Richtlinien an

  - Geben Sie zum Anzeigen von Informationen zu allen PIN-Richtlinien den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsPinPolicy
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern vorhandener Webdienst-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Erstellen einer neuen PIN-Richtlinie in lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


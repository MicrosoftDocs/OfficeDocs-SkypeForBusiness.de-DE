---
title: 'Lync Server 2013: Anzeigen von Zugriffsnummern für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f897e773390cc894b3d9718b5eb354d1d4547a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Anzeigen von Zugriffsnummern für Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

In lync Server 2013 Systemsteuerung stellen Sie den Benutzern Einwahlnummern zur Verfügung, damit Sie extern an einer Besprechung teilnehmen können.

<div>

## <a name="to-view-dial-in-access-numbers"></a>So zeigen Sie Zugriffsnummern für die Einwahl an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.

4.  Klicken Sie auf der Seite **Zugriffsnummer für Einwahlkonferenz** auf die Zugriffsnummer, die Sie anzeigen möchten.

5.  Aktivieren Sie unter **Bearbeiten** das Kontrollkästchen **Details anzeigen**.

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Anzeigen von Zugriffsnummern für Einwahlkonferenzen mithilfe von Windows PowerShell-Cmdlets

Zugriffsnummern für Einwahlkonferenzen können mit Windows PowerShell und dem Cmdlet Get-CsDialInConferencingAccessNumber angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a>So zeigen Sie Zugriffsnummern für Einwahlkonferenzen an

  - Wenn Sie Informationen zu allen Zugriffsnummern für Einwahlkonferenzen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsDialInConferencingAccessNumber
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


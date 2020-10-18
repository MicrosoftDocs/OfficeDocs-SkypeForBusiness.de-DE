---
title: 'Lync Server 2013: Anzeigen von Besprechungs Konfigurationseinstellungen'
description: 'Lync Server 2013: Anzeigen von Besprechungs Konfigurationseinstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190b9d331a8cd0a08e17c482dbc3b0bc27590003
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576401"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Anzeigen von Besprechungs Konfigurationseinstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

In lync Server 2013 Systemsteuerung verwenden Sie die Einstellung für die besprechungskonfiguration, um zu steuern, wie Besprechungen in Ihrer Bereitstellung implementiert werden. Dies umfasst die folgenden Besprechungs Konfigurationen:

  - Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.

  - Optionale Konfigurationen auf Standort-und Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Besprechungen für bestimmte Websites oder Benutzer implementiert werden.

<div>

## <a name="to-view-meeting-configuration-settings"></a>So zeigen Sie die Besprechungs Konfigurationseinstellungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **besprechungskonfiguration** auf die besprechungskonfiguration, die Sie anzeigen möchten.

5.  Wählen Sie unter **Datei Filter bearbeiten**die Option **Details anzeigen aus.** Kontrollkästchen.
    
    **Bearbeiten der besprechungskonfiguration \<policy\> –** Öffnet die Anzeige der Einstellungen für die ausgewählte Richtlinie. Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer Sammlung von Besprechungs Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Besprechungs Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets

Die Besprechungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Get-CsMeetingConfiguration-Cmdlet angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-meeting-configuration-information"></a>So zeigen Sie Besprechungs Konfigurationsinformationen an

  - Wenn Sie Informationen zu allen Besprechungs Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsMeetingConfiguration
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


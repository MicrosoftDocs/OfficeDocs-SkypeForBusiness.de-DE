---
title: 'Lync Server 2013: Anzeigen von Einstellungen für die besprechungskonfiguration'
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
ms.openlocfilehash: 5737fbba63915501bea80105ef3509511d8cb436
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Anzeigen von Einstellungen für die besprechungskonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der lync Server 2013-Systemsteuerung verwenden Sie die Einstellung für die besprechungskonfiguration, um zu steuern, wie Besprechungen in Ihrer Bereitstellung implementiert werden. Dies umfasst die folgenden Besprechungs Konfigurationen:

  - Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Konfigurationen auf Websiteebene und auf Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Besprechungen für bestimmte Websites oder Benutzer implementiert werden.

<div>

## <a name="to-view-meeting-configuration-settings"></a>So zeigen Sie die Einstellungen für die besprechungskonfiguration an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **Besprechungskonfiguration** auf die Besprechungskonfiguration, die Sie anzeigen möchten.

5.  Wählen Sie im **Filter Datei bearbeiten**die Option **Details anzeigen aus.** Aktivieren Sie das Kontrollkästchen.
    
    **Besprechungskonfiguration bearbeiten – \<die\> Richtlinie** wird geöffnet und zeigt die Einstellungen für die ausgewählte Richtlinie an. Details zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer Sammlung von Einstellungen für die besprechungskonfiguration in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zur besprechungskonfiguration mithilfe von Windows PowerShell-Cmdlets

Die Einstellungen für die besprechungskonfiguration können mithilfe von Windows PowerShell und dem Cmdlet Get-CsMeetingConfiguration angezeigt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-view-meeting-configuration-information"></a>So zeigen Sie die Informationen zur besprechungskonfiguration an

  - Wenn Sie Informationen zu allen Besprechungs Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsMeetingConfiguration
    
    Es werden etwa folgende Informationen zurückgegeben:
    
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


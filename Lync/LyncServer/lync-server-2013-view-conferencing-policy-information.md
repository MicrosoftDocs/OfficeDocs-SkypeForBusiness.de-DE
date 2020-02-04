---
title: 'Lync Server 2013: Anzeigen von Konferenzrichtlinien Informationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5c2cccd61d710acd9d2155412ec427c65eafc2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a>Anzeigen von Konferenzrichtlinien Informationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der lync Server 2013-Systemsteuerung verwenden Sie Konferenzrichtlinien, um zu steuern, wie Konferenzen in Ihrer Bereitstellung implementiert werden. Dazu gehören die folgenden Konferenzrichtlinien:

  - Eine globale Richtlinie, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Richtlinie auf Website-und Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Konferenzen für bestimmte Websites oder Benutzer implementiert werden.

<div>

## <a name="to-view-conferencing-policy-settings"></a>So zeigen Sie konferenzrichtlinieneinstellungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **konferenzrichtlinie**.

4.  Doppelklicken Sie auf der Seite **Konferenzrichtlinie** auf die Konferenzrichtlinie, die angezeigt werden soll.

5.  Wählen Sie im **Filter Datei bearbeiten**die Option **Details anzeigen aus.** Aktivieren Sie das Kontrollkästchen.
    
    **Konferenzrichtlinien bearbeiten – \<die\> Richtlinie** wird geöffnet und zeigt die Einstellungen für die ausgewählte Richtlinie an. Details zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Anzeigen von Konferenzrichtlinien mithilfe von Windows PowerShell-Cmdlets

Konferenzrichtlinien können mithilfe von Windows PowerShell und dem Cmdlet Get-CsConferencingPolicy angezeigt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-view-conferencing-policies"></a>So zeigen Sie Konferenzrichtlinien an

  - Wenn Sie Informationen zu allen Konferenzrichtlinien anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsConferencingPolicy
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>


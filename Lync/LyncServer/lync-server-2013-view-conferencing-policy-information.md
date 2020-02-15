---
title: 'Lync Server 2013: Anzeigen von Informationen zur konferenzrichtlinie'
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
ms.openlocfilehash: 7795579564c9ae011b1541d97aee25f3cf206313
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a>Anzeigen von Informationen zu Konferenzrichtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

In lync Server 2013 Systemsteuerung verwenden Sie Konferenzrichtlinien, um zu steuern, wie Konferenzen in Ihrer Bereitstellung implementiert werden. Dies umfasst die folgenden Konferenzrichtlinien:

  - Eine globale Richtlinie, die bei der Bereitstellung von lync Server 2013 standardmäßig erstellt wird.

  - Optionale Richtlinie auf Standort-und Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Konferenzen für bestimmte Websites oder Benutzer implementiert werden.

<div>

## <a name="to-view-conferencing-policy-settings"></a>So zeigen Sie konferenzrichtlinieneinstellungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Konferenzrichtlinie**.

4.  Doppelklicken Sie auf der Seite **konferenzrichtlinie** auf die konferenzrichtlinie, die Sie anzeigen möchten.

5.  Wählen Sie unter **Datei Filter bearbeiten**die Option **Details anzeigen aus.** Kontrollkästchen.
    
    **Konferenzrichtlinie bearbeiten – \<Richt\> Linie** wird geöffnet und zeigt die Einstellungen für die ausgewählte Richtlinie an. Ausführliche Informationen zum Konfigurieren der Einstellungen finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Anzeigen von Konferenzrichtlinien mithilfe von Windows PowerShell-Cmdlets

Konferenzrichtlinien können mit Windows PowerShell und dem Cmdlet Get-CsConferencingPolicy angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-view-conferencing-policies"></a>So zeigen Sie Konferenzrichtlinien an

  - Um Informationen zu allen Konferenzrichtlinien anzuzeigen, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsConferencingPolicy
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
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


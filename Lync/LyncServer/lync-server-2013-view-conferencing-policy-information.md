---
title: Anzeigen von Informationen zu Konferenzrichtlinien
TOCTitle: Anzeigen von Informationen zu Konferenzrichtlinien
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49890988
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Konferenzrichtlinien

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In Systemsteuerung für Lync Server 2013 verwenden Sie Konferenzrichtlinien, um zu steuern, wie Konferenzen in einer Bereitstellung implementiert werden. Dazu gehören die folgenden Konferenzrichtlinien:

  - Eine globale Richtlinie, die standardmäßig erstellt wird, wenn Sie Lync Server 2013 bereitstellen.

  - Optionale Richtlinien auf Standort- und auf Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie Konferenzen für bestimmte Standorte oder Benutzer implementiert werden.

## So zeigen Sie Konferenzrichtlinien an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Konferenzen** und dann auf **Konferenzrichtlinie**.

4.  Doppelklicken Sie auf der Seite **Konferenzrichtlinie** auf die Konferenzrichtlinie, die angezeigt werden soll.

5.  Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Details anzeigen**.
    
    Das Dialogfeld **Konferenzrichtlinie bearbeiten – \<Richtlinie\>** wird geöffnet, in dem die Einstellungen für die ausgewählte Richtlinie angezeigt werden. Einzelheiten zum Konfigurieren dieser Einstellungen finden Sie unter [Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## Anzeigen von Konferenzrichtlinien mithilfe der Lync Server-PowerShell-Cmdlets

Sie können Konferenzrichtlinien auch mithilfe von Lync Server PowerShell und des **Get-CsConferencingPolicy**-Cmdlets anzeigen. Dieses Cmdlet können Sie entweder in der Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Anzeigen von Konferenzrichtlinien

  - Zum Anzeigen von Informationen zu allen Konferenzrichtlinien geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:
    
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

Weitere Informationen finden Sie in dem Hilfethema zum [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy)-Cmdlet.


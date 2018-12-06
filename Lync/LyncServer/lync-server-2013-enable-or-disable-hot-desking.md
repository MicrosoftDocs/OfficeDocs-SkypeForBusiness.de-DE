---
title: Aktivieren oder Deaktivieren von Hotdesking
TOCTitle: Aktivieren oder Deaktivieren von Hotdesking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994057(v=OCS.15)
ms:contentKeyID: 52056405
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren von Hotdesking

 

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Sie können Telefone in öffentlichen Bereichen als *Hotdesking-Telefone* einrichten. Auf Hotdesking-Telefonen können sich Benutzer an ihrem Benutzerkonto anmelden und anschließend Lync Server-Features sowie ihre eigenen Benutzerprofileinstellungen nutzen. Hotdesking wird durch Clientrichtlinien verwaltet: Zum Aktivieren oder Deaktivieren von Hotdesking müssen Sie die Clientrichtlinien für Ihre Telefone in öffentlichen Bereichen ändern. Ausführliche Informationen zur Bestimmung der Konferenzrichtlinien, die Ihren Telefonen in öffentlichen Bereichen zugewiesen sind, finden Sie unter [Anzeigen von Informationen zu Telefonen in öffentlichen Bereichen](lync-server-2013-view-common-area-phone-information.md).

Sie verwenden den EnableHotdesking-Parameter des Cmdlets **New-CSClientPolicy** oder **Set-CSClientPolicy** zum Aktivieren oder Deaktivieren von Hotdesking auf einem Telefon wie folgt. Führen Sie diese beiden Cmdlets entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell aus. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Aktivieren von Hotdesking

  - Zum Aktivieren von Hotdesking für ein Telefon für öffentliche Bereiche müssen Sie die Clientrichtlinie ändern, die diesem Telefon (oder der Auflistung von Telefonen) zugewiesen ist.
    
    Nachdem Sie die zu ändernde Richtlinie ermittelt haben folgt als nächster Schritt die Verwendung des Cmdlets **Set-CsClientPolicy**, um den EnableHotdesking-Parameter auf "True" festzulegen. Beispiel:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Sie können auch das Cmdlet **New-CsClientPolicy** verwenden, um eine neue Clientrichtlinie zum Aktivieren von Hotdesking zu erstellen. Beispiel:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True


> [!IMPORTANT]
> Nachdem diese Richtlinie erstellt wurde, müssen Sie sie den entsprechenden Telefonen in öffentlichen Bereichen zuweisen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Zuweisen von Richtlinien an ein Telefon in einem öffentlichen Bereich</A>.



## Deaktivieren von Hotdesking

  - Legen Sie zum Deaktivieren von Hotdesking für ein Telefon in einem öffentlichen Bereich den Standardwert des EnableHotdesking-Parameters des **Set-CsClientPolicy** auf "False" fest. Beispiel:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

Einzelheiten dazu finden Sie in den Hilfethemen zu den Cmdlets [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) und [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy).


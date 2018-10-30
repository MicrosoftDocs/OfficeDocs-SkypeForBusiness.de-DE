---
title: Erstellen oder Ändern eines Kontaktobjekts für ein Konferenzgerät
TOCTitle: Erstellen oder Ändern eines Kontaktobjekts für ein Konferenzgerät
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994035(v=OCS.15)
ms:contentKeyID: 52056350
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern eines Kontaktobjekts für ein Konferenzgerät

 

_**Letztes Änderungsdatum des Themas:** 2013-10-02_

Zum Erstellen eines Konferenzraumobjekts erstellen Sie zunächst ein Active Directory-Benutzerkonto, welches das Gerät darstellt. Aktivieren Sie dann mithilfe des Cmdlets **Enable-CsMeetingRoom** das Konto für die Funktion als Konferenzgerät. Wenn Sie die Eigenschaften eines vorhandenen Konferenzgeräts ändern müssen, verwenden Sie dazu das Cmdlet **Set-CsMeetingRoom**.

Diese Cmdlets können Sie entweder in der Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.




## Erstellen eines Konferenzgeräts

  - Nachdem Sie das Active Directory-Benutzerkonto erstellt haben, welches das neue Konferenzgerät darstellt, aktivieren Sie es mithilfe des Cmdlets **Enable-CsMeetingRoom**. Achten Sie darauf, Folgendes anzugeben: a) die Identität des Konferenzgeräts, b) den Registrierungsstellenpool, in dem das Raumkonto gehostet wird und c) die SIP-Adresse, die diesem Konto zugewiesen wird. Beispiel:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Ändern eines Konferenzgeräts

  - Verwenden Sie das Cmdlet **Set-CsMeetingRoom**, um die Eigenschaftswerte eines vorhandenen Konferenzgeräts zu ändern. Mit dem folgenden Befehl wird z. B. die Telefonnummer (LineUri) aktualisiert, die einem Konferenzgerät zugewiesen ist:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

Einzelheiten dazu finden Sie in den Hilfethemen zu den Cmdlets [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) und [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom).


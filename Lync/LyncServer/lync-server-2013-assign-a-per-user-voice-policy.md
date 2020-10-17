---
title: 'Lync Server 2013: Zuweisen einer VoIP-Richtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine benutzerspezifische VoIP-Richtlinie zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea0b171e10302b4c466187c54324cc2548e821
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563561"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Zuweisen einer VoIP-Richtlinie pro Benutzer in lync Server 2013

 


VoIP-Richtlinien auf globaler und auf Standortebene werden automatisch allen lync Server 2013 Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind. Sie können VoIP-Richtlinien auch bestimmten Benutzern zuweisen, indem Sie entweder die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell verwenden. Verwenden Sie die Verfahren in diesem Thema, um lync Server Benutzern explizit benutzerspezifische Richtlinien zuzuweisen.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>So weisen Sie eine benutzerspezifische VoIP-Richtlinie mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **VoIP-Richtlinie** die Benutzerrichtlinie aus, die Sie anwenden möchten.
    

    > [!NOTE]  
    > Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen werden die Standardeinstellungen für Server oder globale Richtlinien übernommen.



## <a name="assign-per-user-voice-policies"></a>Zuweisen von VoIP-Richtlinien pro Benutzer

Sie können benutzerspezifische VoIP-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsVoicePolicy** zuweisen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Informationen zum Verwenden von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie in diesem lync Server Windows PowerShell Blogbeitrag: [schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a>Zuweisen einer benutzerbasierten VoIP-Richtlinie zu einem einzelnen Benutzer

  - Der folgende Befehl weist die benutzerbasierte VoIP-Richtlinie "RedmondVoicePolicy" dem Benutzer "Ken Myer" zu.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a>Zuweisen einer VoIP-Richtlinie für einzelne Benutzer zu mehreren Benutzern

  - Der folgende Befehl weist die benutzerbasierte VoIP-Richtlinie "FinanceVoicePolicy" allen Benutzern zu, die Konten in der OU "Finance" in Active Directory haben. Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a>Aufheben der Zuweisung einer VoIP-Richtlinie pro Benutzer

  - Der folgende Befehl hebt die Zuweisung der dem Benutzer "Ken Myer" zuvor zugewiesenen VoIP-Richtlinie auf. Nachdem die Zuweisung der benutzerbasierten Richtlinie aufgehoben ist, wird Ken Myer automatisch über die globale Richtlinie oder, sofern vorhanden, seine lokale Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsVoicePolicy-](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) Cmdlet.

## <a name="see-also"></a>Siehe auch


[Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 Management-Shell](lync-server-2013-lync-server-management-shell.md)


---
title: 'Lync Server 2013: Zuweisen einer beständigen Chat Richtlinie für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 616a171d4aedcc6014ddea3c5993a097d410a5e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722825"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Zuweisen einer beständigen Chat Richtlinie für einzelne Benutzer in lync Server 2013

 


Sie können der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell eine Richtlinie für beständigen Chat pro Benutzer zuweisen. Details zum Erstellen von Benutzerrichtlinien für beständigen Chat Server finden Sie unter [Erstellen einer Benutzerrichtlinie für beständigen Chat in lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>So weisen Sie eine Richtlinie für beständigen Chat für einzelne Benutzer mit der lync Server-Systemsteuerung zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
      - Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
    4.  Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein oder klicken Sie auf den Pfeil in der Dropdownliste.
        

        > [!TIP]  
        > Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.

    
    5.  Klicken Sie auf **Suchen**.

6.  Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.
    

    > [!TIP]  
    > Wenn Sie möchten, dass die gleiche Richtlinie für Benutzer mit beständigem Chat für mehrere Benutzer gilt, wählen Sie in den Suchergebnissen mehrere Benutzer aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>, und klicken Sie dann auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie in Richt **Linien zuweisen**unter Richtlinien für **beständigen Chat**eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren <STRONG> &lt;&gt; </STRONG> können, ist für jede Richtlinie im Dialogfeld standardmäßig beibehalten aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Wählen ** \<Sie\> automatisch** aus, damit lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene auswählen kann.
    
      - Klicken Sie auf den Namen einer auf der Seite für **beständigen Chats** festgelegten beständigen Chat Richtlinie für einzelne Benutzer.
        

        > [!TIP]  
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer beständigen Chat Richtlinie für einzelne Benutzer mithilfe von Windows PowerShell-Cmdlets

Mithilfe des Cmdlets **Grant-CsPersistentChatPolicy** können Sie auch beständige Chat-Richtlinien für einzelne Benutzer zuweisen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Richtlinie für beständigen Chat pro Benutzer zu

  - Mit dem folgenden Befehl wird dem Benutzer Ken Myers die Richtlinie für den beständigen Chat für einzelne Benutzer zugewiesen RedmondPersistentChatPolicy.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für beständigen Chat pro Benutzer zu

  - Dieser Befehl weist allen Benutzern, die für die IT-Abteilung arbeiten, die Richtlinien für die beständigen Chat-RedmondUsersPersistentChatPolicy zu. Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>So heben Sie die Zuweisung einer beständigen Chat Richtlinie für einzelne Benutzer auf

  - Mit dem folgenden Befehl wird die Zuweisung einer beständigen Chat Richtlinie für einzelne Benutzer aufheben, die Ken Myers zuvor zugewiesen wurde. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) .

## <a name="see-also"></a>Siehe auch


[Erstellen einer Benutzerrichtlinie für beständigen Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)


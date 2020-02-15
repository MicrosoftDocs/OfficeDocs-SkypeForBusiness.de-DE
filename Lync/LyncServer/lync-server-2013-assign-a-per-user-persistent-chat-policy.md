---
title: 'Lync Server 2013: Zuweisen einer Richtlinie für den beständigen Chat pro Benutzer'
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
ms.openlocfilehash: 335f14018e9e489dbb6ca4db5a4d6138eb330faf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030128"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Zuweisen einer Richtlinie für beständigen Chat pro Benutzer in lync Server 2013

 


Sie können eine Richtlinie für beständigen Chat auf Benutzerbasis entweder lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell zuweisen. Ausführliche Informationen zum Erstellen von Benutzerrichtlinien für den Server für beständigen Chat finden Sie unter [Erstellen einer Benutzerrichtlinie für beständigen Chat in lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>So weisen Sie eine Richtlinie für beständigen Chat auf Benutzer lync Server-Systemsteuerung zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
      - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
    4.  Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.
        

        > [!TIP]  
        > Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.

    
    5.  Klicken Sie auf **Suchen**.

6.  Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.
    

    > [!TIP]  
    > Wenn Sie dieselbe benutzerbasierte Richtlinie für beständigen Chat auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Richtlinie für beständigen Chat** eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren <STRONG> &lt;&gt; </STRONG> können, ist für jede Richtlinie im Dialogfeld standardmäßig beizubehalten aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Wählen ** \<Sie\> automatisch** aus, damit lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Standortebene auswählen kann.
    
      - Klicken Sie auf der Seite **Richtlinie für beständigen Chat** auf den Namen einer benutzerbasierten Richtlinie für beständigen Chat, die Sie zuvor definiert haben.
        

        > [!TIP]  
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Richtlinie für beständigen Chat auf Benutzerbasis mithilfe Windows PowerShell-Cmdlets

Sie können auch benutzerspezifische Richtlinien für beständigen Chat mithilfe des Cmdlets **Grant-cspersistentchatpolicy "** zuweisen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Richtlinie für den beständigen Chat pro Benutzer zu

  - Mit dem folgenden Befehl wird die benutzerbasierte Richtlinie für beständigen Chat RedmondPersistentChatPolicy dem Benutzer Ken Myer zugewiesen.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für den beständigen Chat pro Benutzer zu

  - Mit diesem Befehl wird dem Benutzer, der für die IT-Abteilung arbeitet, die Richtlinie für den RedmondUsersPersistentChatPolicy für beständigen Chat zugewiesen. Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>So heben Sie die Zuweisung einer Richtlinie für beständigen Chat pro Benutzer auf

  - Mit dem folgenden Befehl wird jede benutzerbasierte Richtlinie für beständigen Chat, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-cspersistentchatpolicy "-](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) Cmdlet.

## <a name="see-also"></a>Siehe auch


[Erstellen einer Benutzerrichtlinie für den beständigen Chat in lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)


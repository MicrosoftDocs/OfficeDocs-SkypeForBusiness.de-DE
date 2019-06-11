---
title: 'Lync Server 2013: Zuweisen einer clientversionsrichtlinie für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bfd26aff4ae2e5d8dacf7ec145bec0e3247facf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839753"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Zuweisen einer clientversionsrichtlinie pro Benutzer in lync Server 2013

 


Die clientversionsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung konfigurieren können.

Das Bereitstelleneiner oder mehrerer clientversionsrichtlinien für einzelne Benutzer ist optional. Sie können auch nur eine clientversionsrichtlinie auf globaler Ebene oder clientversionsrichtlinien auf Websiteebene oder auf Poolebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine bestimmte Richtlinie auf Websiteebene, Poolebene oder pro Benutzer zugewiesen ist, werden die Standard Clients, die bei lync Server 2013 registriert werden können, in den clientversionsrichtlinien auf globaler Ebene definiert.

Nachdem Sie mindestens eine clientversionsrichtlinie für einzelne Benutzer erstellt haben, verwenden Sie die Verfahren in diesem Thema, um die Richtlinie zuzuweisen, die die Clientversionen angibt, die Sie für die Registrierung bei lync Server zulassen möchten.

Details zum Erstellen von clientversionsrichtlinien für einzelne Benutzer finden Sie unter [angeben der Clientanwendungen, die für die Anmeldung bei lync Server 2013 verwendet werden können](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>So weisen Sie eine clientversionsrichtlinie pro Benutzer zu

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
    > Wenn Sie möchten, dass die gleiche clientversionsrichtlinie für einzelne Benutzer auf mehrere Benutzer angewendet wird, wählen Sie in den Suchergebnissen mehrere Benutzer aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>, und klicken Sie dann auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie in **Richtlinien zuweisen**unter **Client Versionsrichtlinie**eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren <STRONG> &lt;&gt; </STRONG> können, ist für jede Richtlinie im Dialogfeld standardmäßig beibehalten aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Zulassen, dass lync Server automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene oder auf Poolebene wählt.
    
      - Klicken Sie auf den Namen der benutzerdefinierten clientversionsrichtlinie, die Sie zuvor auf der Seite **clientversionsrichtlinie** definiert haben.
        

        > [!TIP]  
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Client Versionsrichtlinie für einzelne Benutzer mithilfe von Windows PowerShell-Cmdlets

Mithilfe des Cmdlets Grant-CsClientVersionPolicy können Sie clientversionsrichtlinien für einzelne Benutzer zuweisen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine clientversionsrichtlinie pro Benutzer zu

  - Mit dem folgenden Befehl wird dem Benutzer Ken Myers die Richtlinie für benutzerspezifische clientversionsrichtlinien RedmondClientVersionPolicy zugewiesen.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für die benutzerspezifische Client Version zu

  - Dieser Befehl weist allen Benutzern, denen zurzeit die VoIP-Richtlinien RedmondVoicePolicy zugewiesen sind, die Richtlinien für die Benutzer-RedmondClientVersionPolicy-Client Version zu. Weitere Informationen zu dem in diesem Befehl verwendeten Filter Parameter finden Sie in der Dokumentation für das Cmdlet " [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) ".
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>So heben Sie die Zuweisung einer clientversionsrichtlinie für einzelne Benutzer auf

  - Mit dem folgenden Befehl wird die Zuweisung einer benutzerseitigen clientversionsrichtlinie, die Ken Myers zuvor zugewiesen wurde, aufheben. Nachdem die Richtlinie für einzelne Benutzer nicht zugewiesen wurde, wird Ken Myers automatisch mithilfe der globalen Richtlinie, seiner lokalen Website Richtlinie (sofern vorhanden) oder der seiner Registrierungsstelle zugewiesenen Dienstbereichs Richtlinie verwaltet. Eine Dienstbereichs Richtlinie hat Vorrang vor jeder Website Richtlinie, und eine Website Richtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Siehe auch


[Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)


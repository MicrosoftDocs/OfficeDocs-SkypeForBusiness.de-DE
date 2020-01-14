---
title: 'Lync Server 2013: Zuweisen einer pro-Benutzer-Archivierungsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d23e44e397a77f0d490d8fda27ee711d1c61c5
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111579"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Zuweisen einer pro-Benutzer-Archivierungsrichtlinie in lync Server 2013

 


Die Archivierungsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server 2013-Systemsteuerung konfigurieren können.

Die Bereitstellung einer oder mehrerer Archivierungsrichtlinien für einzelne Benutzer ist optional. Sie können auch nur eine Archivierungsrichtlinie auf globaler Ebene oder eine Archivierungsrichtlinie auf Websiteebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Archivierungsanforderungen werden automatisch auf die in der konferenzrichtlinie auf globaler Ebene festgelegten Standardeinstellungen angewendet, wenn keine spezifische Richtlinie für Websiteebene oder einzelne Benutzer zugewiesen ist.

Nachdem Sie mindestens eine Archivierungsrichtlinie für einzelne Benutzer erstellt haben, verwenden Sie die Verfahren in diesem Thema, um die Richtlinie zuzuweisen, die entsprechend angibt, ob die interne Kommunikation, die externe Kommunikation oder beides vom Server archiviert wird.

Details zum Erstellen von Archivierungsrichtlinien für einzelne Benutzer finden Sie unter [Erstellen einer Archivierungsrichtlinie in lync Server 2013, um die Archivierung interner oder externer Kommunikation für bestimmte Websites oder Benutzer zu aktivieren oder zu deaktivieren](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>So weisen Sie eine Archivierungsrichtlinie für einzelne Benutzer zu

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
    > Wenn dieselbe Archivierungsrichtlinie für einzelne Benutzer auf mehrere Benutzer angewendet werden soll, wählen Sie in den Suchergebnissen mehrere Benutzer aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>, und klicken Sie dann auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie in **Richtlinien zuweisen**unter **Archivierungsrichtlinie**eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren <STRONG> &lt;&gt; </STRONG> können, ist für jede Richtlinie im Dialogfeld standardmäßig beibehalten aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Erlauben Sie lync Server 2013, automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene zu wählen.
    
      - Klicken Sie auf den Namen einer pro-Benutzer-Archivierungsrichtlinie, die Sie zuvor auf der Seite **Archivierungsrichtlinie** definiert haben.
        

        > [!TIP]  
        > Wenn Sie bei der Entscheidung über die Richtlinie helfen möchten, die Sie zuweisen möchten, klicken Sie nach dem Klicken auf einen Richtliniennamen auf <STRONG>Ansicht</STRONG> , um die in der Richtlinie definierten Benutzerrechte und Berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer pro-Benutzer-Archivierungsrichtlinie mithilfe von Windows PowerShell-Cmdlets

Sie können Archivierungsrichtlinien für einzelne Benutzer mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsArchivingPolicy** zuweisen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Archivierungsrichtlinie pro Benutzer zu

  - Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ dem Benutzer Jonas Baar zugeordnet.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>So weisen Sie eine Archivierungsrichtlinie für einzelne Benutzer mehreren Benutzern zu

  - Dieser Befehl weist allen Benutzern, die Konten im Registrierungspool ATL-CS-001.litwareinc.com haben, die Archivierungsrichtlinien für einzelne Benutzer zu RedmondArchivingPolicy. Weitere Informationen zu dem in diesem Befehl verwendeten Filter Parameter finden Sie in der Dokumentation für das Cmdlet " [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) ".
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>So heben Sie die Zuweisung einer pro-Benutzer-Archivierungsrichtlinie auf

  - Mit dem folgenden Befehl wird die Zuweisung einer pro-Benutzer-Archivierungsrichtlinie, die Ken Myers zuvor zugewiesen wurde, aufheben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .

## <a name="see-also"></a>Siehe auch


[Erstellen einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung interner oder externer Kommunikation für bestimmte Websites oder Benutzer](lync-server-2013-create-archiving-policy-sites-users.md)  


[Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)


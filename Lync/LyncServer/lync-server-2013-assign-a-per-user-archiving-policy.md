---
title: 'Lync Server 2013: Zuweisen einer Archivierungsrichtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine benutzerspezifische Archivierungsrichtlinie zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559991"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Zuweisen einer benutzerbasierten Archivierungsrichtlinie in lync Server 2013

 


Die Archivierungsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server 2013-Systemsteuerung konfigurieren können.

Die Bereitstellung einer oder mehrerer Archivierungsrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine Archivierungsrichtlinie auf globaler oder Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer definiert wurde, werden automatisch die Archivierungsanforderungen in der globalen Konferenzrichtlinie verwendet.

Nachdem Sie mindestens eine Archivierungsrichtlinie auf Benutzerebene erstellt haben, können Sie anhand der Verfahren in diesem Thema diese Richtlinie zuweisen, mit der gemäß Ihren Anforderungen angegeben wird, ob die interne und/oder externe Kommunikation eines bestimmten Benutzers vom Server archiviert wird.

Ausführliche Informationen zum Erstellen von benutzerspezifischen Archivierungsrichtlinien finden Sie unter [Erstellen einer Archivierungsrichtlinie in lync Server 2013, um die Archivierung der internen oder externen Kommunikation für bestimmte Websites oder Benutzer zu aktivieren oder zu deaktivieren](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>So weisen Sie eine Archivierungsrichtlinie auf Benutzerebene zu

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
    > Wenn Sie dieselbe Benutzerarchivierungsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Archivierungsrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beizubehalten</STRONG> aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Zulassen, dass lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Standortebene auswählen.
    
      - Klicken Sie auf der Seite **Archivierungsrichtlinie** auf den Namen einer Archivierungsrichtlinie auf Benutzerebene, die Sie zuvor definiert haben.
        

        > [!TIP]  
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Per-User Archivierungsrichtlinie mithilfe von Windows PowerShell-Cmdlets

Sie können benutzerspezifische Archivierungsrichtlinien zuweisen, indem Sie Windows PowerShell und das **Grant-CsArchivingPolicy-** Cmdlet verwenden. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine benutzerspezifische Archivierungsrichtlinie zu

  - Mit dem folgenden Befehl wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" dem Benutzer "Ken Myer" zugewiesen.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine benutzerspezifische Archivierungsrichtlinie zu

  - Mithilfe dieses Befehls wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" allen Benutzern zugeordnet, deren Konten im Registrar-Pool "atl-cs-001.litwareinc.com" verwaltet werden. Weitere Informationen zum in diesem Befehl verwendeten Filter-Parameter finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>So heben Sie die Zuweisung einer benutzerbasierten Archivierungsrichtlinie auf

  - Der folgende Befehl hebt alle bestehenden Zuweisungen von benutzerbezogenen Archivierungsrichtlinien zu "Ken Myer" auf. Danach wird Ken Myer automatisch von der globalen Richtlinie oder, wenn vorhanden, von der Richtlinie für seinen lokalen Standort verwaltet. (Standortrichtlinien haben Vorrang vor der globalen Richtlinie).
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsArchivingPolicy-](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) Cmdlet.

## <a name="see-also"></a>Siehe auch


[Erstellen einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung interner oder externer Kommunikation für bestimmte Websites oder Benutzer](lync-server-2013-create-archiving-policy-sites-users.md)  


[Zuweisen von Richtlinien pro Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)


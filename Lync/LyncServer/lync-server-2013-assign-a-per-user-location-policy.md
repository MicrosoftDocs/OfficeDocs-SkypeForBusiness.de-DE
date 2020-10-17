---
title: 'Lync Server 2013: Zuweisen einer Standortrichtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine ortungsrichtlinie pro Benutzer zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81631740e0a6c908c392ccacb6b37d7033d9224c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559881"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Zuweisen einer Standortrichtlinie pro Benutzer in lync Server 2013

 


Die ortungsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung konfigurieren können.

Die Bereitstellung einer oder mehrerer Ortungsrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine Ortungsrichtlinie auf globaler oder auf Subnetzebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. E9-1-1-Einstellungen werden standardmäßig auf die in der Ortungsrichtlinie auf globaler Ebene definierten Einstellungen festgelegt, wenn keine spezifische Richtlinie auf Subnetz- oder Benutzerebene zugewiesen wird.

Nach Erstellung mindestens einer Ortungsrichtlinie auf Benutzerebene führen Sie die Schritte in diesem Thema aus, um die Richtlinie mit den Einstellungen zuzuweisen, die der Server auf Notrufe von einem bestimmten Benutzer anwenden soll.

Eine Liste aller verfügbaren Standortrichtlinien Einstellungen finden Sie unter [Definieren der ortungsrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Ausführliche Informationen zum Erstellen von ortungsrichtlinien finden Sie unter [Create Location Policies in lync Server 2013](lync-server-2013-create-location-policies.md).

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>So weisen Sie eine benutzerspezifische ortungsrichtlinie dem lync Server-Systemsteuerung zu

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
    > Wenn Sie dieselbe Benutzerortungsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Ortungsrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beizubehalten</STRONG> aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Zulassen, dass lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Subnetzebene wählt.
    
      - Klicken Sie auf den Namen einer Benutzerortungsrichtlinie, die Sie zuvor durch Ausführen des Cmdlets **New-CsLocationPolicy** definiert haben.
        

        > [!TIP]  
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Zuweisen einer Per-User ortungsrichtlinie mithilfe von lync Server-Verwaltungsshell-Cmdlets

Sie können benutzerspezifische ortungsrichtlinien zuweisen, indem Sie das Grant-CsLocationPolicy-Cmdlet verwenden. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>So weisen Sie eine benutzerbasierte Standortrichtlinie einem einzelnen Benutzer zu

  - Mit dem folgenden Befehl wird die benutzerbasierte Standortrichtlinie RedmondLocationPolicy dem Benutzer Ken Myer zugewiesen.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>So weisen Sie eine benutzerbasierte Standortrichtlinie mehreren Benutzern zu

  - Mit diesem Befehl wird die benutzerspezifische ortungsrichtlinie AccountingDepartmentLocationPolicy allen Benutzern zugewiesen, die für die Buchhaltungsabteilung arbeiten. Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>So heben Sie die Zuweisung der benutzerbasierten Standortrichtlinie auf

  - Mit dem folgenden Befehl wird die für den Benutzer Ken Myer vorgenommene Zuweisung einer benutzerbasierten Standortrichtlinie aufgehoben. Nach dem Aufheben der benutzerbasierten Standortrichtlinie wird Ken Myer automatisch mithilfe der globalen Richtlinie verwaltet oder, sofern vorhanden, mit der ihm zugewiesenen lokalen Standortrichtlinie. Eine Standortrichtlinie hat Vorrang vor einer globalen Richtlinie.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsLocationPolicy-](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) Cmdlet.


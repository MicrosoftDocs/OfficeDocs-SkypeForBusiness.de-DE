---
title: 'Lync Server 2013: Zuweisen einer Mobilitätsrichtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine benutzerspezifische Mobilitätsrichtlinie zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b17c58cf3477002a7fa43035b72c77963663316
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559831"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Zuweisen einer benutzerbezogenen Mobilitätsrichtlinie in lync Server 2013

 


Die Mobilitätsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in lync Server-Systemsteuerung oder lync Server-Verwaltungsshell konfigurieren können.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>So weisen Sie eine benutzerspezifische Mobilitätsrichtlinie lync Server-Systemsteuerung zu

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
    > Wenn Sie dieselbe benutzerbasierte Mobilitätsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Mobilitätsrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie in <STRONG>Zuweisungsrichtlinien</STRONG>konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beizubehalten</STRONG> aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Aktivieren Sie **\<Automatic\>** diese Option, damit lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Standortebene auswählen kann.
    
      - Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf den Namen einer benutzerbasierten Mobilitätsrichtlinie, die Sie zuvor definiert haben.
        

        > [!TIP]  
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Per-User Mobilitätsrichtlinie mithilfe von Windows PowerShell-Cmdlets

Sie können benutzerspezifische mobilitätsrichtlinien zuweisen, indem Sie Windows PowerShell und das **Grant-CsMobilityPolicy-** Cmdlet verwenden. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine benutzerbasierte Mobilitätsrichtlinie zu

  - Mit dem folgenden Befehl wird die benutzerbasierte Mobilitätsrichtlinie RedmondMobilityPolicy dem Benutzer Ken Myer zugewiesen.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine benutzerbasierte Mobilitätsrichtlinie zu

  - Mit dem folgenden Befehl wird die benutzerspezifische Mobilitätsrichtlinie RedmondMobilityPolicy allen Benutzern zugewiesen, denen derzeit die Richtlinie NorthAmericaMobilityPolicy zugeordnet ist. Ausführliche Informationen zu dem in diesem Befehl verwendeten Filter-Parameter finden Sie unter [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>So heben Sie die Zuweisung einer benutzerbasierten Mobilitätsrichtlinie auf

  - Mit dem folgenden Befehl wird jede benutzerbasierte Mobilitätsrichtlinie, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Ausführliche Informationen finden Sie unter [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Siehe auch


[Konfigurieren von mobilitätsrichtlinien in lync Server 2013](lync-server-2013-configuring-mobility-policy.md)


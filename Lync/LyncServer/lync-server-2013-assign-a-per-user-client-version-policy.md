---
title: 'Lync Server 2013: Zuweisen einer clientversionsrichtlinie pro Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3668e21836fd3ecee0740493c8b9bd631227583a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029266"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Zuweisen einer clientversionsrichtlinie pro Benutzer in lync Server 2013

 


Die clientversionsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung konfigurieren können.

Die Bereitstellung einer oder mehrerer clientversionsrichtlinien pro Benutzer ist optional. Sie können auch nur eine clientversionsrichtlinie auf globaler Ebene oder clientversionsrichtlinien auf Websiteebene oder Poolebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine bestimmte Richtlinie auf Website-, Pool-oder Benutzerebene zugewiesen ist, werden die Standard Clients, die sich bei lync Server 2013 registrieren dürfen, in der clientversionsrichtlinie auf globaler Ebene definiert.

Nachdem Sie mindestens eine clientversionsrichtlinie pro Benutzer erstellt haben, weisen Sie anhand der Verfahren in diesem Thema die Richtlinie zu, die die Clientversionen angibt, die Sie für die Registrierung mit lync Server zulassen möchten.

Ausführliche Informationen zum Erstellen von clientversionsrichtlinien pro Benutzer finden Sie unter [angeben der Clientanwendungen, die für die Anmeldung bei lync Server 2013 verwendet werden können](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>So weisen Sie eine clientversionsrichtlinie pro Benutzer zu

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
    > Wenn Sie dieselbe clientversionsrichtlinie auf Benutzerbasis auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>und dann auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie in **Richtlinien zuweisen**unter **Client Versionsrichtlinie**eine der folgenden Aktionen aus:
    

    > [!NOTE]  
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren <STRONG> &lt;&gt; </STRONG> können, ist für jede Richtlinie im Dialogfeld standardmäßig beizubehalten aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Zulassen, dass lync Server automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Standortebene oder auf Poolebene auswählen.
    
      - Klicken Sie auf der Seite **clientversionsrichtlinie** auf den Namen einer benutzerbasierten clientversionsrichtlinie, die Sie zuvor definiert haben.
        

        > [!TIP]  
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Client Versionsrichtlinie auf Benutzerbasis mithilfe Windows PowerShell-Cmdlets

Sie können benutzerbasierte clientversionsrichtlinien zuweisen, indem Sie das Grant-CsClientVersionPolicy-Cmdlet verwenden. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine clientversionsrichtlinie pro Benutzer zu

  - Mit dem folgenden Befehl wird dem Benutzer Ken Myers die clientversionsrichtlinie für die benutzerspezifische RedmondClientVersionPolicy zugewiesen.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine clientversionsrichtlinie pro Benutzer zu

  - Mit diesem Befehl wird die benutzerbasierte clientversionsrichtlinie RedmondClientVersionPolicy allen Benutzern zugewiesen, denen derzeit die VoIP-Richtlinie "redmondvoicepolicy" zugeordnet ist. Weitere Informationen zum in diesem Befehl verwendeten Filter-Parameter finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>So heben Sie die Zuweisung einer clientversionsrichtlinie pro Benutzer auf

  - Mit dem folgenden Befehl wird die Zuweisung einer clientversionsrichtlinie für einzelne Benutzer aufgehoben, die Ken Myers zuvor zugewiesen wurde. Nachdem die Zuweisung der benutzerbezogenen Richtlinie aufgehoben wurde, wird Ken Myers automatisch mithilfe der globalen Richtlinie, seiner lokalen Standortrichtlinie (sofern vorhanden) oder der seiner Registrierungsstelle zugewiesenen Dienstbereichs Richtlinie verwaltet. Eine Dienstbereichs Richtlinie hat Vorrang vor jeder Standortrichtlinie, und eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsClientVersionPolicy-](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) Cmdlet.

## <a name="see-also"></a>Siehe auch


[Zuweisen von Richtlinien pro Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)


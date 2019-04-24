---
title: Weisen Sie eine benutzerbasierte PIN-Richtlinie in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Zusammenfassung: Phase AV- und OAuth Zertifikate für Skype für Business Server.'
ms.openlocfilehash: ec2187ddf75d3725646ed9ea732a65552d432364
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211093"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Weisen Sie eine benutzerbasierte PIN-Richtlinie in Skype für Business Server

**Zusammenfassung:** Phase AV- und OAuth-Zertifikaten für Skype für Business Server.
  
Die Richtlinien für einwahlkonferenzen persönliche Identifikationsnummer (PIN) ist eine der Einstellungen für ein Benutzerkonto, das in der Skype für Business Server-Systemsteuerung konfiguriert werden können.
  
Die Bereitstellung einer oder mehrerer PIN-Richtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine globale PIN-Richtlinie oder eine PIN-Richtlinie auf Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer zugewiesen wurde, gelten automatisch die Benutzerrechte und Berechtigungen im Hinblick auf die Verwendung von PINs für Einwahlkonferenzen, die in der globalen PIN-Richtlinie definiert sind.
  
Nachdem Sie mindestens eine PIN-Richtlinie auf Benutzerebene erstellt haben, weisen Sie sie mithilfe der Verfahren in diesem Thema zu. Die zugewiesene Richtlinie gibt die Einschränkungen an, die der Server auf die PIN-Erstellung und -Verwendung durch einen bestimmten Benutzer anwenden soll.
  
### <a name="to-assign-a-per-user-pin-policy"></a>So weisen Sie eine PIN-Richtlinie auf Benutzerebene zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
   - Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.
    
   - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.
    
5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:
    
   a. Klicken Sie auf **Filter hinzufügen**.
    
   b. Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
   c. Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
   d. Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein oder klicken Sie auf den Pfeil in der Dropdownliste.
    
    > [!TIP]
    > Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben. 
  
   e. Klicken Sie auf **Suchen**.
    
6. Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.
    
    > [!TIP]
    > Wenn Sie dieselbe PIN-Richtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf **Aktionen** und anschließend auf **Richtlinien zuweisen**. 
  
7. Führen Sie im Abschnitt **Richtlinien zuweisen** unter **PIN-Richtlinie** eine der folgenden Aktionen aus:
    
    > [!NOTE]
    > Da es mehrere Richtlinien, die Sie konfigurieren können sind, über das Dialogfeld **Richtlinien zuweisen** ** \<zu belassen wie ist\> ** ist standardmäßig für jede Richtlinie in das Dialogfeld aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.
  
   - Zulassen von Skype für Business Server automatisch auswählen Auswahl die globalen Richtlinie oder, falls definiert, die Richtlinie auf Standortebene.
    
   - Klicken Sie auf der Seite **PIN-Richtlinie** auf den Namen einer PIN-Richtlinie auf Benutzerebene, die Sie zuvor definiert haben.
    
     > [!TIP]
     > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf **Anzeigen**, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.
  
8. Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer PIN-Richtlinie pro Benutzer mithilfe von Windows PowerShell-Cmdlets

Sie können pro-Benutzer-PIN-Richtlinien zuweisen, mithilfe von Windows PowerShell und das Cmdlet **Grant-CsPinPolicy** . Sie können dieses Cmdlet ausführen, von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine benutzerbasierte PIN-Richtlinie zu

- Mit dem folgenden Befehl wird die benutzerbasierte PIN-Richtlinie RedmondPinPolicy dem Benutzer Ken Myer zugewiesen.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine benutzerbasierte PIN-Richtlinie zu

- Mit dem folgenden Befehl wird die benutzerbasierte Richtlinie RedmondUsersPinPolicy allen Benutzern in der Stadt Redmond zugewiesen. Ausführliche Informationen zu den Parameter "LdapFilter" in diesem Befehl verwendet finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>So heben Sie die Zuweisung einer benutzerbasierten PIN-Richtlinie auf

- Mit dem folgenden Befehl wird jede benutzerbasierte PIN-Richtlinie, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Weitere Informationen hierzu finden Sie unter [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Siehe auch

[Erstellen Sie eine neue PIN-Richtlinie in Skype für Business Server](create-a-new-pin-policy.md)

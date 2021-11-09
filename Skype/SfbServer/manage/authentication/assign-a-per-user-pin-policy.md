---
title: Zuweisen einer benutzerbasierten PIN-Richtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Zusammenfassung: Bereitstellen von AV- und OAuth-Zertifikaten für Skype for Business Server.'
ms.openlocfilehash: 51bf650d907923c83801799a28220eae9a1f385c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845478"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Zuweisen einer benutzerbasierten PIN-Richtlinie in Skype for Business Server

**Zusammenfassung:** Bereitstellen von AV- und OAuth-Zertifikaten für Skype for Business Server.
  
Die PIN-Richtlinie (Persönliche Identifikationsnummer) für Einwahlkonferenzen ist eine der individuellen Einstellungen eines Benutzerkontos, die in der Skype for Business Server Systemsteuerung konfiguriert werden können.
  
Die Bereitstellung einer oder mehrerer PIN-Richtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine globale PIN-Richtlinie oder eine PIN-Richtlinie auf Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer zugewiesen wurde, gelten automatisch die Benutzerrechte und Berechtigungen im Hinblick auf die Verwendung von PINs für Einwahlkonferenzen, die in der globalen PIN-Richtlinie definiert sind.
  
Nachdem Sie mindestens eine PIN-Richtlinie auf Benutzerebene erstellt haben, weisen Sie sie mithilfe der Verfahren in diesem Thema zu. Die zugewiesene Richtlinie gibt die Einschränkungen an, die der Server auf die PIN-Erstellung und -Verwendung durch einen bestimmten Benutzer anwenden soll.
  
### <a name="to-assign-a-per-user-pin-policy"></a>So weisen Sie eine PIN-Richtlinie auf Benutzerebene zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
   - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
   - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.
    
5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
   a. Klicken Sie auf **Filter hinzufügen**.
    
   b. Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
   c. Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
   d. Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.
    
    > [!TIP]
    > Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben. 
  
   e. Klicken Sie auf **Suchen**.
    
6. Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.
    
    > [!TIP]
    > Wenn Sie dieselbe PIN-Richtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf **Aktionen** und anschließend auf **Richtlinien zuweisen**. 
  
7. Führen Sie im Abschnitt **Richtlinien zuweisen** unter **PIN-Richtlinie** eine der folgenden Aktionen aus:
    
    > [!NOTE]
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds **"Richtlinien zuweisen"** konfigurieren können, **\<Keep as is\>** ist es standardmäßig für jede Richtlinie im Dialogfeld ausgewählt. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.
  
   - Zulassen, dass Skype for Business Server automatisch entweder die globale Richtlinie oder, falls definiert, die Richtlinie auf Standortebene auswählen.
    
   - Klicken Sie auf der Seite **PIN-Richtlinie** auf den Namen einer PIN-Richtlinie auf Benutzerebene, die Sie zuvor definiert haben.
    
     > [!TIP]
     > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf **Anzeigen**, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.
  
8. Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Per-User PIN-Richtlinie mithilfe Windows PowerShell Cmdlets

Sie können benutzerspezifische PIN-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsPinPolicy** zuweisen. Sie können dieses Cmdlet aus der Skype for Business Server-Verwaltungsshell oder aus einer Remotesitzung mit Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie unter [Microsoft Lync Remote PowerShell Administration.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine benutzerbasierte PIN-Richtlinie zu

- Mit dem folgenden Befehl wird die benutzerbasierte PIN-Richtlinie RedmondPinPolicy dem Benutzer Ken Myer zugewiesen.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine benutzerbasierte PIN-Richtlinie zu

- Der folgende Befehl weist die benutzerbasierte PIN-Richtlinie "RedmondUsersPinPolicy" allen Benutzern zu, die in der Stadt Redmond arbeiten. Ausführliche Informationen zum in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>So heben Sie die Zuweisung einer benutzerbasierten PIN-Richtlinie auf

- Mit dem folgenden Befehl wird jede benutzerbasierte PIN-Richtlinie, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Ausführliche Informationen finden Sie unter [Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Siehe auch

[Erstellen einer neuen PIN-Richtlinie in Skype for Business Server](create-a-new-pin-policy.md)
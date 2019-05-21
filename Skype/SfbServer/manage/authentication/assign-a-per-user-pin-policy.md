---
title: Zuweisen einer pro-Benutzer-PIN-Richtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Zusammenfassung: Stage AV-und OAuth-Zertifikate für Skype for Business Server.'
ms.openlocfilehash: dafb70239552b9ee2c5e84e7624e881711e8ce6f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278356"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Zuweisen einer pro-Benutzer-PIN-Richtlinie in Skype for Business Server

**Zusammenfassung:** Stage AV-und OAuth-Zertifikate für Skype for Business Server.
  
Die Richtlinie für Einwahlkonferenzen (persönliche Identifikationsnummer) ist eine der individuellen Einstellungen eines Benutzerkontos, das in der Skype for Business Server-Systemsteuerung konfiguriert werden kann.
  
Die Bereitstellung einer oder mehrerer PIN-Richtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine globale PIN-Richtlinie oder eine PIN-Richtlinie auf Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer zugewiesen wurde, gelten automatisch die Benutzerrechte und Berechtigungen im Hinblick auf die Verwendung von PINs für Einwahlkonferenzen, die in der globalen PIN-Richtlinie definiert sind.
  
Nachdem Sie mindestens eine PIN-Richtlinie auf Benutzerebene erstellt haben, weisen Sie sie mithilfe der Verfahren in diesem Thema zu. Die zugewiesene Richtlinie gibt die Einschränkungen an, die der Server auf die PIN-Erstellung und -Verwendung durch einen bestimmten Benutzer anwenden soll.
  
### <a name="to-assign-a-per-user-pin-policy"></a>So weisen Sie eine PIN-Richtlinie auf Benutzerebene zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
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
    > Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds **Richtlinien zuweisen** konfigurieren ** \<\> ** können, ist für jede Richtlinie im Dialogfeld standardmäßig beibehalten aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.
  
   - Erlauben Sie Skype for Business Server, automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene zu wählen.
    
   - Klicken Sie auf der Seite **PIN-Richtlinie** auf den Namen einer PIN-Richtlinie auf Benutzerebene, die Sie zuvor definiert haben.
    
     > [!TIP]
     > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf **Anzeigen**, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.
  
8. Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer pro-Benutzer-PIN-Richtlinie mithilfe von Windows PowerShell-Cmdlets

Sie können benutzerspezifische PIN-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsPinPolicy** zuweisen. Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine benutzerbasierte PIN-Richtlinie zu

- Mit dem folgenden Befehl wird die benutzerbasierte PIN-Richtlinie RedmondPinPolicy dem Benutzer Ken Myer zugewiesen.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine benutzerbasierte PIN-Richtlinie zu

- Mit dem folgenden Befehl wird die benutzerbasierte Richtlinie RedmondUsersPinPolicy allen Benutzern in der Stadt Redmond zugewiesen. Details zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>So heben Sie die Zuweisung einer benutzerbasierten PIN-Richtlinie auf

- Mit dem folgenden Befehl wird jede benutzerbasierte PIN-Richtlinie, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Ausführliche Informationen finden Sie unter [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Siehe auch

[Erstellen einer neuen PIN-Richtlinie in Skype for Business Server](create-a-new-pin-policy.md)

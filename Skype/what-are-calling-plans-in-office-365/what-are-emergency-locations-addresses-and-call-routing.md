---
title: "Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.AddressAndLocation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
description: "Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. "
---

# Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?

Wenn Sie Anrufpläne in Office 365 konfigurieren, müssen Sie jeder Telefonnummer eine Notfalladresse zuweisen, um Notrufe zu unterstützen. Dies muss geschehen, wenn Sie die Telefonnummer erwerben oder wenn Sie sie einem Benutzer zuweisen. Bevor Sie eine Notfalladresse einer Telefonnummer zuweisen, müssen Sie die Notfalladresse erstellen und validieren. Durch die Validierung wird sichergestellt, dass die Notfalladresse erkannt wird, das heißt, dass sie im richtigen Format vorliegt, das von Notdiensten verwendet werden kann. Optional kann innerhalb der Notfalladresse ein Standort hinzugefügt werden, um den Standort des Benutzers genauer anzugeben. Als Notfallstandort können Sie zum Beispiel ein Stockwerk, einen Flügel oder ein Büro mit einer bestimmten Notfalladresse verknüpfen. Im Gegensatz zu Notfalladressen werden Standorte nicht validiert.
  
## Was sind Notfalladressen?

Eine Notfalladresse ist für aktive Telefonnummern erforderlich, dies hängt jedoch vom Land bzw. der Region ab. In den USA ist eine Notfalladresse **erforderlich**, wenn eine Nummer einem Benutzer zugewiesen wird. In anderen Ländern wie etwa in Europa, dem Nahen Osten und Afrika (EMEA) ist eine Notfalladresse **erforderlich**, wenn Sie die Telefonnummer über Office 365 erhalten oder wenn die Telefonnummer von einem anderen Dienstanbieter oder Netzbetreiber übertragen wird.
  
Eine Notfalladresse wird häufig als Adresse, Postanschrift oder physische Adresse bezeichnet. Es handelt sich um die Postanschrift oder Adresse eines Bürostandorts Ihrer Organisation. Zum Beispiel wird die Adresse  *12345 North Main Street, Redmond, WA 98052, USA*  verwendet, um Notrufe an die entsprechenden Einsatzleitstellen weiterzuleiten und den Standort des Anrufers zu ermitteln. Wenn Ihr Unternehmen mehrere physische Standorte hat, benötigen Sie wahrscheinlich mehrere Notfalladressen.
  
Beim Validieren einer Notfalladresse wird sichergestellt, dass die Adresse legitim und für Notdienste richtig formatiert ist. Es ist zwar möglich, eine Notfalladresse zu erstellen und zu speichern, ohne diese zu validieren, jedoch können nur validierte Adressen einem Benutzer zugewiesen werden. Sobald eine Notfalladresse validiert und gespeichert ist, kann sie einem Benutzer zugewiesen werden. Wenn Sie eine gespeicherte und validierte Notfalladresse ändern möchten, müssen Sie eine neue Notfalladresse erstellen.
  
## Was sind Notfallstandorte?

Notfallstandorte werden mit einer Notfalladresse verknüpft, um den genauen Standort innerhalb eines Gebäudes anzugeben. Ein Notfallstandort kann die Nummer eines Stockwerks, Gebäudeflügels oder Büros sein, in dem sich der Benutzer befindet. Sie können beliebig viele Standorte mit einer Notfalladresse verknüpfen.
  
Wenn Sie einem Benutzer eine Notfalladresse zuweisen, handelt es sich eigentlich um eine Standort-ID, die referenziert wird, wenn Sie die Adresse zuweisen. Die Standort-ID enthält die Notfalladresse (die Postanschrift oder Adresse). Jede Notfalladresse erhält einen Standardnotfallstandort für den Fall, dass keine Standorte innerhalb des Gebäudes erforderlich sind. 
  
## Was ist Notrufweiterleitung?

Notfalladressen und -standorte werden beim Weiterleiten von Notrufen an die entsprechende Rettungsleitstelle verwendet, wenn diese Ersthelfer entsendet. Wenn Skype for Business-Benutzer eine Notrufnummer wählen, hängt es vom Land bzw. der Region ab, wie der Anruf an den zuständigen PSAP (Public Safety Answering Point) weitergeleitet wird. In einigen Ländern bzw. Regionen wie beispielsweise den USA und dem Vereinigten Königreich werden die Anrufe zunächst überprüft, um den aktuellen Standort des Benutzers zu ermitteln. Erst dann wird die Verbindung mit der zuständigen Rettungsleitstelle hergestellt. In anderen Ländern/Regionen werden Notrufe direkt an die Rettungsleitstelle weitergeleitet. Dabei wird die Telefonnummer übermittelt, die dem Anrufer zugeordnet ist.
  
## Erstellen, Hinzufügen und Zuweisen von Notfallstandorten und Notfalladressen für Ihre Benutzer

1. **Planen von Notfallstandorten** Im ersten Schritt planen Sie Ihre Notfallstandorte. Sie müssen alle Ihre physischen Adressen aufführen. Auf dieser Grundlage ermitteln Sie dann, ob Standorte für die Notfalladressen erforderlich sind und um welche es sich gegebenenfalls handelt. Wenn ein Unternehmen zum Beispiel drei Bürogebäude mit je vier Stockwerken besitzt, werden wahrscheinlich drei Notfalladressen mit jeweils den Stockwerken 1 bis 4 als Standorte benötigt.
    
2. **Erstellen und Überprüfen der Notfallstandorte** Der nächste Schritt besteht darin, die Notfalladressen zu erstellen und zu überprüfen. Sie können eine Notfalladresse bei der Erstellung überprüfen. Weitere Informationen zum Erstellen einer Notfalladresse finden Sie unter[Hinzufügen oder Löschen einer Notfalladresse für Ihr Unternehmen](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Durch die Validierung einer Postanschrift oder Adresse wird sichergestellt, dass die Adresse legitim und richtig formatiert ist. Es ist möglich, dass eine teilweise korrekte Notfalladresse, wie z. B. ein falsch geschriebener Name einer Stadt, bei der Validierung anerkannt wird. Die Validierung bestimmt anhand aller Teile der jeweiligen Adresse, ob genug Informationen enthalten sind, um den Anruf an die entsprechende Rettungsleitstelle weiterzuleiten. Wenn dies der Fall ist, wird sie als validiert zurückgegeben und kann dann einer Telefonnummer zugewiesen werden. 
  
3. **Beziehen von Telefonnummern** Der nächste Schritt besteht darin, Telefonnummern für Ihre Benutzer zu beziehen. Dazu können Sie neue Telefonnummern über Office 365 beziehen oder vorhandene Telefonnummern portieren, das heißt nach Office 365 übertragen. Die vollständigen Schritte können Sie sich unter[Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md) ansehen.
    
4. **Zuweisen von Telefonnummern** Der letzte Schritt besteht darin, Benutzern das Tätigen und Annehmen von Telefonanrufen zu ermöglichen. Dazu müssen Sie jedem Benutzer eine Telefonnummer zuweisen. Wie Sie eine Telefonnummer zuweisen, erfahren Sie unter[Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](assign-change-or-remove-a-phone-number-for-a-user.md).
    
## Siehe auch

#### Weitere Ressourcen

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
  
[Audio-Konferenzen Grußformeln durchführen Periode](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)


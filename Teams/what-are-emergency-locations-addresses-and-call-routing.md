---
title: Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 55a19854b3b95d7f8dfac711412041ee06a9d890
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853359"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?

Wenn Sie plant Aufrufen in Office 365 konfigurieren, ist es erforderlich, dass jede Telefonnummer eine Notfall-Adresse zugewiesen werden, wenn Sie entweder die Telefonnummer abrufen oder seine zugewiesenen zu einem Benutzer zur Unterstützung von notrufdienste. Bevor Sie eine Telefonnummer ein Notruf-Adresse zuweisen, muss eine Notfall-Adresse erstellt und überprüft werden. Überprüfung wird sichergestellt, dass die Notfall Adresse erkannt wird und im richtigen Format ist, die von den Diensten für Notfallmaßnahmen verwendet werden können. Optional kann ein Speicherort innerhalb der Notfall Adresse hinzugefügt werden, um eine bestimmte Position für den Benutzer bereitzustellen. Beispielsweise könnte der Notruf Speicherort ein Floor, Flügel oder Office, die mit einer bestimmten Notfall Adresse verknüpft ist. Obwohl Notfall Adresse überprüft werden, sind nicht Speicherorte.
  
## <a name="what-are-emergency-addresses"></a>Was sind Notfalladressen?

Eine Notfall-Adresse ist erforderlich für die aktive Telefonnummern, aber wenn erforderlich ist das Land/Region abhängig. In den USA ist eine Notfall-Adresse **erforderlich** , wenn eine Zahl, die einem Benutzer zugewiesen ist. Für andere Länder ist wie in Europa, dem Nahen Osten und Afrika (EMEA), eine Notfall-Adresse **erforderlich** , wenn erhalten Sie die Telefonnummer von Office 365 oder wenn er von einer anderen Dienstanbieter oder Netzbetreiber übertragen wird.
  
Eine Notfall Adresse kann als eine Anschrift, Straße oder eine physische Adresse bezeichnet werden. Es ist die Postanschrift oder Anschrift eines Bürostandorts Ihres Unternehmens. Beispielsweise die Adresse, die *12345 North Main Street, Redmond, WA 98052* zum Weiterleiten von Notrufen an den entsprechenden Versendung Behörden und zur Unterstützung bei der Suche nach den Notruf tätigt verwendet wird. Wenn Ihr Unternehmen mehrere physische Standorte hat, benötigen Sie wahrscheinlich mehrere Notfalladressen.
  
Eine Notruf Adresse validieren umfasst, und stellen Sie sicher, dass es sich um legitime und für Notfallmaßnahmen Services richtig formatiert ist. Es ist möglich, erstellen und speichern Sie eine Notfall Adresse, die wird nicht überprüft, aber nur überprüfte Adressen können ein Benutzer zugeordnet werden. Sobald eine Notfalladresse geprüft und gespeichert ist, kann sie einem Benutzer zugewiesen werden. Wenn Sie eine gespeicherte und überprüfte Notfalladresse ändern möchten, müssen Sie eine neue Notfalladresse erstellen.
  
## <a name="what-are-emergency-locations"></a>Was sind Notfallstandorte?

Notfallstandorten sind eine Notfall-Adresse Geben Sie eine genauere Standort Gebäude zugeordnet. Ein Notfallstandort kann ein Stockwerk, ein Gebäudeflügel oder die Nummer eines Büros sein, in dem sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von einem Notfall Adresse zugeordneten Speicherorte haben. 
  
Wenn Sie einem Benutzer eine Notfalladresse zuweisen, ist es eigentlich eine Standort-ID, die referenziert wird, wenn Sie die Adresse zuweisen. Die ID enthält die referenzierte Notfall Adresse (Straße oder allgemeinen-Adresse). Jede Notfalladresse erhält einen Standardnotfallstandort für den Fall, dass keine Standorte im Gebäude erforderlich sind. 
  
## <a name="what-is-emergency-call-routing"></a>Was ist Notrufweiterleitung?

Notfall-Adressen und Speicherorte werden beim ersten entsendet abgesetzt während der Verarbeitung Weiterleitung von Notrufen an der Mitte des entsprechenden Versendung verwendet werden. Wenn eine Skype für Geschäftsbenutzer eine Notrufnummer wählt, variieren wie der Anruf an die Bereitstellung von öffentlichen Sicherheit beantworten Point (PSAP) weitergeleitet wird nach Land/Region. In einigen Ländern wie den USA und im Vereinigten Königreich werden die Anrufe zuerst überwacht werden, um den aktuellen Speicherort des Benutzers zu bestimmen, bevor Sie den Anruf an das entsprechende Versendung Center anschließen. In anderen Ländern/Regionen werden Anrufe direkt zum Übermitteln von Suchabfragen die den Notruf tätigt zugeordnete Telefonnummer Versendung Center weitergeleitet.
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>Erstellen, hinzufügen und Zuweisen von notfallstandorten und Adressen für Ihre Benutzer

1. **Planen von notfallstandorten** Der erste Schritt ist zum Planen der notfallstandorte. Sie müssen alle Ihre physischen Adressen aufgeführt. Klicken Sie dann auf Grundlage, ermittelt, ob die Speicherorte für die Notfall-Adressen erforderlich sind, und wenn Ja, was sind. Beispielsweise wenn ein Unternehmen 3 Bürogebäude jedes mit 4 Etagen aufweist, ist es wahrscheinlich, dass es 3 Notfall Adressen mit Etagen 1 bis 4 für jede als Speicherort aufgeführt werden müssen.
    
2. **Erstellen und Überprüfen der Notfallstandorte** Der nächste Schritt besteht darin, die Notfalladressen zu erstellen und zu überprüfen. Sie können eine Notfalladresse bei der Erstellung überprüfen. Zum Erstellen einer Notfall Adresse finden Sie unter [Hinzufügen oder entfernen, die einem Notfall Webadresse für Ihre Organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > Überprüfen der allgemeinen Straße oder die Adresse eine umfasst, und stellen Sie sicher, dass es sich um legitime und richtig formatiert ist. Es ist möglich, dass eine teilweise korrekte Notfalladresse, wie z. B. ein falsch geschriebener Name einer Stadt, bei der Validierung anerkannt wird. Validierungsprozess verwendet alle Teile einer angegebenen Adresse um zu ermitteln, ob sie über ausreichend Informationen zum Weiterleiten des Anrufs im entsprechenden Notfällen Center enthält. Ist dies der Fall ist, wird als überprüft zurückgegeben und dann an eine Telefonnummer zugewiesen werden können. 
  
3. **Abrufen von Telefonnummern** Der nächste Schritt besteht darin Rufnummern für Ihre Benutzer abzurufen. Dies ist durch die erste neue Telefonnummern von Office 365 oder durch "Portieren" oder übertragen Ihre vorhandenen Telefonnummern über an Office 365 möglich. Die vollständigen Schritte finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Zuweisen von Telefonnummern** Der letzte Schritt besteht darin, Benutzern das Tätigen und Annehmen von Telefonanrufen zu ermöglichen. Dazu müssen Sie jedem Benutzer eine Telefonnummer zuweisen. Finden Sie unter [zuweisen, ändern oder entfernen Sie eine Rufnummer für einen Benutzer](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user) an eine Telefonnummer zuweisen.

> [!NOTE]
> Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Verwandte Themen
[Was ist Adressvalidierung?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Verschiedene Arten von Telefonnummern für Anrufpläne](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)


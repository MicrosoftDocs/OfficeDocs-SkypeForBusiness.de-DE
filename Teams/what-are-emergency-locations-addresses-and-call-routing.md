---
title: Was sind notfallstandorten, Adressen und Anrufrouting?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 4e9fd0d3fa9fabc1f9b2176a4dc2b7ac59206352
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541984"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Was sind notfallstandorten, Adressen und Anrufrouting?

Wenn Sie Pläne Aufrufen in Office 365 konfigurieren, müssen Sie jede Telefonnummer eine Notfall Adresse zuweisen, wenn Sie die Rufnummer erhalten oder eines Benutzers zur Unterstützung von notrufdienste zuweisen. Und bevor Sie eine Adresse Notruf an eine Telefonnummer zuweisen können, müssen Sie erstellen und überprüfen Sie die Notfall-Adresse. Überprüfung wird sichergestellt, dass die Notfall Adresse erkannt wird und im richtigen Format ist, die von den Diensten für Notfallmaßnahmen verwendet werden können. Optional können Sie einen Speicherort innerhalb der Notfall Adresse anzugebende eine bestimmte Position für den Benutzer hinzufügen. Beispielsweise könnte der Notruf Speicherort ein Floor, Flügel oder Office, die mit einer bestimmten Notfall Adresse verknüpft ist. Obwohl Notfall Adresse überprüft werden, sind nicht Speicherorte.
  
## <a name="what-are-emergency-addresses"></a>Was sind Notfalladressen?

Eine Notfall-Adresse ist erforderlich für die aktive Telefonnummern, aber wenn es erforderlich ist, hängt davon ab, das Land/Region. In den USA ist eine Notfall-Adresse erforderlich, wenn eine Zahl, die einem Benutzer zugewiesen ist. Für andere Länder ist wie in Europa, dem Nahen Osten und Afrika (EMEA), eine Notfall-Adresse erforderlich, wenn erhalten Sie die Telefonnummer von Office 365 oder wenn er von einer anderen Dienstanbieter oder Netzbetreiber übertragen wird.
  
Eine Notfall Adresse kann als eine Anschrift, Straße oder eine physische Adresse bezeichnet werden. Es ist die Postanschrift oder Anschrift eines Bürostandorts Ihres Unternehmens. Beispielsweise die Adresse, die *12345 North Main Street, Redmond, WA 98052* zum Weiterleiten von Notrufen an den entsprechenden Versendung Behörden und zur Unterstützung bei der Suche nach den Notruf tätigt verwendet wird. Wenn Ihr Unternehmen mehrere physische Standorte hat, benötigen Sie wahrscheinlich mehrere Notfalladressen.
  
Eine Notruf Adresse validieren umfasst, und stellen Sie sicher, dass es sich um legitime und für Notfallmaßnahmen Services richtig formatiert ist. Es ist möglich, erstellen und speichern Sie eine Notfall Adresse, die wird nicht überprüft, aber nur überprüfte Adressen können ein Benutzer zugeordnet werden. Sobald eine Notfalladresse geprüft und gespeichert ist, kann sie einem Benutzer zugewiesen werden. Wenn Sie eine gespeicherte und überprüfte Notfalladresse ändern möchten, müssen Sie eine neue Notfalladresse erstellen.
  
## <a name="what-are-emergency-locations"></a>Was sind Notfallstandorte?

Ein Notfall Speicherort ist eine Notfall-Adresse Geben Sie eine genauere Standort Gebäude zugeordnet. Ein Notfallstandort kann ein Stockwerk, ein Gebäudeflügel oder die Nummer eines Büros sein, in dem sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von einem Notfall Adresse zugeordneten Speicherorte haben. 
  
Wenn Sie einem Benutzer eine Notfall-Adresse zuweisen, ist es tatsächlich einen Standort-ID, auf die verwiesen wird, wenn Sie die Adresse zuweisen. Die ID enthält die referenzierte Notfall Adresse (Straße oder allgemeinen-Adresse). Ein Standardspeicherort für den Notfall gehört zum Lieferumfang von einer Notfall-Adresse für den Fällen, in denen in Erstellen von Speicherorten nicht erforderlich sind. 
  
## <a name="what-is-emergency-call-routing"></a>Was ist Notrufweiterleitung?

Notfall-Adressen und Speicherorte werden beim ersten entsendet abgesetzt während der Verarbeitung Weiterleitung von Notrufen an der Mitte des entsprechenden Versendung verwendet werden. Wenn eine Teams oder Skype für Geschäftsbenutzer wählt eine Notrufnummer, wie der Anruf an die Bereitstellung von öffentlichen Sicherheit beantworten Point (PSAP) weitergeleitet wird, hängt nach Land/Region. In einigen Ländern wie den USA und im Vereinigten Königreich werden die Anrufe zuerst überwacht werden, um den aktuellen Speicherort des Benutzers zu bestimmen, bevor Sie den Anruf an das entsprechende Versendung Center anschließen. In anderen Ländern/Regionen werden Anrufe direkt zum Übermitteln von Suchabfragen die den Notruf tätigt zugeordnete Telefonnummer Versendung Center weitergeleitet.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Erstellen Sie, fügen Sie hinzu, und weisen Sie notfallstandorten und Adressen für Ihre Benutzer

1. **Planen der notfallstandorte**. Der erste Schritt ist zum Planen der notfallstandorte. Sie müssen alle Ihre physischen Adressen aufgeführt. Klicken Sie dann auf Grundlage, ermittelt, ob die Speicherorte für die Notfall-Adressen erforderlich sind, und wenn Ja, was sind. Beispielsweise wenn ein Unternehmen 3 Bürogebäude jedes mit 4 Etagen aufweist, ist es wahrscheinlich, dass es 3 Notfall Adressen mit Etagen 1 bis 4 für jede als Speicherort aufgeführt werden müssen.
    
2. **Erstellen und überprüfen Sie Ihre notfallstandorten**. Im nächste Schritt wird zum Erstellen und überprüfen Ihre Notfall-Adressen. Sie können eine Notfalladresse bei der Erstellung überprüfen. Zum Erstellen einer Notfall Adresse finden Sie unter [Hinzufügen oder entfernen, die einem Notfall Webadresse für Ihre Organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > Überprüfen der allgemeinen Straße oder die Adresse eine umfasst, und stellen Sie sicher, dass es sich um legitime und richtig formatiert ist. Es ist möglich, dass eine teilweise richtige Notfall Adresse, beispielsweise einen Tippfehler Namen der Stadt ein, weiterhin Validierung kann. Validierungsprozess verwendet alle Teile einer angegebenen Adresse um zu ermitteln, ob sie über ausreichend Informationen zum Weiterleiten des Anrufs im entsprechenden Notfällen Center enthält. Ist dies der Fall ist, wird als überprüft zurückgegeben und dann an eine Telefonnummer zugewiesen werden können. 
  
3. **Abrufen von Rufnummern**. Der nächste Schritt besteht darin Rufnummern für Ihre Benutzer abzurufen. Dies ist durch die erste neue Telefonnummern von Office 365 oder durch "Portieren" oder übertragen Ihre vorhandenen Telefonnummern über an Office 365 möglich. Die vollständigen Schritte finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Zuweisen von Rufnummern**. Der letzte Schritt besteht, damit Benutzer tätigen und Entgegennehmen von Anrufen. Dazu müssen Sie jedem Benutzer eine Telefonnummer zuweisen. Finden Sie unter [zuweisen, ändern oder entfernen Sie eine Rufnummer für einen Benutzer](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user) an eine Telefonnummer zuweisen.

> [!NOTE]
> Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Verwandte Themen
[Was ist Adressvalidierung?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Verschiedene Arten von Telefonnummern für Anrufpläne](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)


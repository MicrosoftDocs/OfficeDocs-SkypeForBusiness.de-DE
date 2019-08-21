---
title: Was sind Notfall Standorte, Adressen und Anrufweiterleitung?
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 979fab1cd099d568278efd61d06a3f8a75b04541
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483863"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Was sind Notfall Standorte, Adressen und Anrufweiterleitung?

Wenn Sie Anrufpläne in Office 365 konfigurieren, müssen Sie jeder Telefonnummer eine Notfalladresse zuweisen, wenn Sie entweder die Telefonnummer erhalten oder Sie einem Benutzer zuweisen, um Notrufe zu unterstützen. Bevor Sie einer Telefonnummer eine Notfalladresse zuweisen können, müssen Sie die Notfalladresse erstellen und überprüfen. Durch die Überprüfung wird sichergestellt, dass die Notfalladresse erkannt wird und dass Sie in einem korrekten Format ist, das von Notfalldiensten verwendet werden kann. Optional können Sie einen Speicherort in der Notfalladresse hinzufügen, um einen spezifischeren Standort für den Benutzer bereitzustellen. Bei dem Notfall Standort kann es sich beispielsweise um eine Boden-, Flügel-oder Bürofläche handeln, die mit einer bestimmten Notfalladresse verknüpft ist. Obwohl Notfalladressen überprüft werden, gibt es keine Speicherorte.
  
## <a name="what-are-emergency-addresses"></a>Was sind Notfalladressen?

Für aktive Telefonnummern ist eine Notfalladresse erforderlich, die aber je nach Land/Region erforderlich ist. In den Vereinigten Staaten ist eine Notfalladresse erforderlich, wenn einem Benutzer eine Nummer zugewiesen wird. Für andere Länder wie in Europa, dem Nahen Osten und Afrika (EMEA) ist eine Notfalladresse erforderlich, wenn Sie die Telefonnummer von Office 365 erhalten oder wenn Sie von einem anderen Dienstanbieter oder Netzbetreiber übertragen wird.
  
Eine Notfalladresse kann als bürgerliche Adresse, Straßenadresse oder eine physikalische Adresse bezeichnet werden. Es ist die Postanschrift oder Anschrift eines Bürostandorts Ihres Unternehmens. So wird beispielsweise die Adresse *12345 North Main Street, Redmond, WA 98052* verwendet, um Notrufe an die entsprechenden Versand Behörden weiterzuleiten und den Notruf Anruf zu unterstützen. Wenn Ihr Unternehmen mehrere physische Standorte hat, benötigen Sie wahrscheinlich mehrere Notfalladressen.
  
Bei der Überprüfung einer Notfalladresse müssen Sie sicherstellen, dass Sie für Notrufdienste legitim und ordnungsgemäß formatiert ist. Es ist möglich, eine Notfalladresse zu erstellen und zu speichern, die nicht überprüft wurde, aber nur validierte Adressen können einem Benutzer zugeordnet werden. Sobald eine Notfalladresse geprüft und gespeichert ist, kann sie einem Benutzer zugewiesen werden. Wenn Sie eine gespeicherte und überprüfte Notfalladresse ändern möchten, müssen Sie eine neue Notfalladresse erstellen.
  
## <a name="what-are-emergency-locations"></a>Was sind Notfallstandorte?

Ein Notfall Standort ist mit einer Notfalladresse verbunden, um eine genauere Position innerhalb eines Gebäudes zu erhalten. Ein Notfallstandort kann ein Stockwerk, ein Gebäudeflügel oder die Nummer eines Büros sein, in dem sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von Speicherorten haben, die einer Notfalladresse zugeordnet sind. 
  
Wenn Sie einem Benutzer eine Notfalladresse zuweisen, handelt es sich tatsächlich um eine Standort-ID, auf die verwiesen wird, wenn Sie die Adresse zuweisen. Die Standort-ID enthält die referenzierte Notfalladresse (die Straßen-oder staatsbürgerliche Adresse). Für Fälle, in denen Baustellen nicht benötigt werden, ist ein Standard Notfall Standort in der Notfalladresse enthalten. 
  
## <a name="what-is-emergency-call-routing"></a>Was ist Notrufweiterleitung?

Notfalladressen und-Standorte werden während der Weiterleitung von Notrufen an das entsprechende Dispatch Center verwendet, wenn Notfall-Ersthelfer entsandt werden. Wenn ein Team oder ein Skype for Business-Benutzer eine Notrufnummer wählt, wird der Anruf an den öffentlichen Sicherheits-Anrufbeantworter (PSAP) je nach Land/Region variieren. In einigen Ländern wie den Vereinigten Staaten und dem Vereinigten Königreich werden die Anrufe zunächst abgeschirmt, um den aktuellen Standort des Benutzers zu ermitteln, bevor Sie den Anruf mit dem entsprechenden Dispatch Center verbinden. In anderen Ländern/Regionen werden Anrufe direkt an das Dispatch Center weitergeleitet, das die Telefonnummer des Notruf Anrufers bedient.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Erstellen, hinzufügen und Zuweisen von Notfall Standorten und-Adressen für Ihre Benutzer

1. **Planen Sie Notfall Standorte**. Der erste Schritt besteht darin, Ihre Notfall Standorte zu planen. Sie müssen alle Ihre physikalischen Adressen auflisten. Wählen Sie dann auf der Grundlage dieser Option aus, ob Speicherorte für die Notfalladressen benötigt werden und was Sie sind. Wenn beispielsweise in einem Unternehmen drei Office-Gebäude mit jeweils 4 Etagen vorhanden sind, ist es wahrscheinlich, dass es 3 Notfalladressen geben muss, wobei die Etagen 1-4 als Standort für jede Liste aufgeführt sind.
    
2. **Erstellen und validieren Sie Ihre Notfall Standorte**. Der nächste Schritt besteht darin, ihre Notfalladressen zu erstellen und zu überprüfen. Sie können eine Notfalladresse bei der Erstellung überprüfen. Informationen zum Erstellen einer Notfalladresse finden Sie unter [Hinzufügen oder Entfernen einer Notfalladresse für Ihre Organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > Zum Überprüfen einer Straßen-oder bürgerlichen Adresse müssen Sie sicherstellen, dass Sie seriös und ordnungsgemäß formatiert ist. Es ist möglich, dass eine teilweise korrekte Notfalladresse, beispielsweise ein falsch eingegebener Name des Orts, weiterhin die Validierung durchlaufen kann. Der Überprüfungsprozess verwendet alle Teile einer bestimmten Adresse, um festzustellen, ob er genügend Informationen enthält, um den Anruf an das entsprechende Notfall-Dispatch-Center weiterzuleiten. Wenn dies der Fall ist, wird Sie als validiert zurückgegeben und kann dann einer Telefonnummer zugewiesen werden. 
  
3. **Holen Sie sich Telefonnummern**. Der nächste Schritt besteht darin, Telefonnummern für Ihre Benutzer zu erhalten. Sie können dies tun, indem Sie neue Telefonnummern von Office 365 oder durch "portieren" oder übertragen Ihrer vorhandenen Telefonnummern auf Office 365. Die vollständigen Schritte finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Zuweisen von Telefonnummern** Der letzte Schritt besteht darin, es Benutzern zu ermöglichen, Telefonanrufe zu tätigen und zu empfangen. Dazu müssen Sie jedem Benutzer eine Telefonnummer zuweisen. Informationen zum Zuweisen einer Telefonnummer finden Sie unter [zuweisen, ändern oder Entfernen einer Telefonnummer für einen Benutzer](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Wenn Sie mehr als die angegebenen Telefonnummern benötigen, lesen Sie [Kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Verwandte Themen
[Was ist Adressvalidierung?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)


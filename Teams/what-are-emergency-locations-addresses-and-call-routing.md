---
title: Was sind Notfall Standorte, Orte und Anrufweiterleitung?
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
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Informieren Sie sich, welche Notfall Standorte, Orte und Notfall-Anrufweiterleitung sind und wie Sie diese planen und ihren Benutzern zuweisen. '
ms.openlocfilehash: 7ab3c17e6d74d8e53358f91b3f99759cf4b22203
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396402"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>Was sind Notfall Standorte, Orte und Anrufweiterleitung?

Wenn Sie Anrufpläne konfigurieren, müssen Sie jeder Telefonnummer einen Notfall Standort zuweisen, wenn Sie entweder die Telefonnummer erhalten oder Sie einem Benutzer zuweisen, um Notrufe zu unterstützen. Bevor Sie einer Telefonnummer einen Notfall Standort zuweisen können, müssen Sie einen Notfall Standort hinzufügen und überprüfen. Durch die Überprüfung wird sichergestellt, dass der Notfall Standort erkannt wird und dass er in einem korrekten Format vorliegt und von Notfalldiensten verwendet werden kann. Optional können Sie einen Ort innerhalb des Notfall Standorts hinzufügen, um einen spezifischeren Standort für den Benutzer bereitzustellen. Bei dem Ort kann es sich beispielsweise um eine Boden-, Flügel-oder Bürofläche handeln, die mit einem bestimmten Notfall Standort verknüpft ist. Obwohl Notfall Speicherorte überprüft werden, gibt es keine Orte.
  
## <a name="what-are-emergency-locations"></a>Was sind Notfallstandorte?

Für aktive Telefonnummern ist ein Notfall Standort erforderlich, je nach Land/Region. In den Vereinigten Staaten ist ein Notfall Standort erforderlich, wenn einem Benutzer eine Nummer zugewiesen wird. Für andere Länder wie in Europa, dem Nahen Osten und Afrika (EMEA) ist ein Notfall Standort erforderlich, wenn Sie die Telefonnummer von Office 365 erhalten oder wenn Sie von einem anderen Dienstanbieter oder Netzbetreiber übertragen wird.
  
Ein Notfall Standort kann als bürgerliche Adresse, Anschrift oder physikalische Adresse bezeichnet werden. Es handelt sich um die Straßen-oder staatsbürgerliche Adresse eines Geschäfts Orts für Ihre Organisation. So wird beispielsweise die Adresse *12345 North Main Street, Redmond, WA 98052* verwendet, um Notrufe an die entsprechenden Versand Behörden weiterzuleiten und den Notruf Anruf zu unterstützen. Es ist wahrscheinlich, dass Sie mehr als einen Notfall Standort benötigen, wenn Ihr Unternehmen über mehr als einen physischen Unternehmensstandort verfügt.
  
Bei der Überprüfung eines Notfall Standorts muss sichergestellt sein, dass es für Notfalldienste legitim und ordnungsgemäß formatiert ist. Es ist möglich, einen Notfall Standort hinzuzufügen und zu speichern, der nicht überprüft wird, aber nur validierte Speicherorte können einem Benutzer zugeordnet werden. Nachdem ein Notfall Standort überprüft und gespeichert wurde, können Sie ihn einem Benutzer zuweisen. Wenn Sie einen Notfall Speicherort ändern möchten, der gespeichert und überprüft wurde, müssen Sie eine neue erstellen.
  
## <a name="what-are-places"></a>Was sind Orte?

Ein Ort ist mit einem Notfall Standort verknüpft, um eine genauere Position innerhalb eines Gebäudes zu erhalten. Ein Ort ist in der Regel ein Stockwerk, ein Gebäudeflügel oder eine Büronummer, in der sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von Orten haben, die mit einem Notfall Standort verknüpft sind. 
  
Wenn Sie einem Benutzer einen Notfall Standort zuweisen, handelt es sich tatsächlich um eine Standort-ID, auf die verwiesen wird, wenn Sie den Standort zuweisen. Die Standort-ID enthält den referenzierten Notfall Standort (die Straßen-oder staatsbürgerliche Adresse). In Fällen, in denen Baustellen nicht benötigt werden, ist ein standardmäßiger Ort in einem Notfall Standort enthalten.
  
## <a name="what-is-emergency-call-routing"></a>Was ist Notrufweiterleitung?

Notfall Standorte und-Orte werden während der Weiterleitung von Notrufen an das entsprechende Dispatch Center verwendet, wenn Notfall-Ersthelfer entsandt werden. Wenn ein Teams-Benutzer eine Notrufnummer anwählt, wird der Anruf an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) je nach Land und Region unterschiedlich weitergeleitet. In einigen Ländern wie den Vereinigten Staaten und dem Vereinigten Königreich werden die Anrufe zunächst abgeschirmt, um den aktuellen Standort des Benutzers zu ermitteln, bevor Sie den Anruf mit dem entsprechenden Dispatch Center verbinden. In anderen Ländern und Regionen werden Anrufe direkt an das Dispatch Center weitergeleitet, das die Telefonnummer des Notruf Anrufers bedient.
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>Erstellen, hinzufügen und Zuweisen von Notfall Standorten und-Orten für Ihre Benutzer

1. **Planen Sie Notfall Standorte**. Der erste Schritt besteht darin, Ihre Notfall Standorte zu planen. Alle Ihre physikalischen Adressen auflisten. Wählen Sie dann auf der Grundlage dieser Funktion aus, ob Orte für die Notfall Standorte erforderlich sind, und wenn ja, was Sie sind. Wenn beispielsweise in einem Unternehmen drei Office-Gebäude mit jeweils vier Etagen vorhanden sind, ist es wahrscheinlich, dass es drei Notfall Standorte geben muss, wobei die Etagen eins bis vier als Ort für jede Person aufgeführt sind.
    
2. **Fügen Sie Ihre Notfall Standorte hinzu**. Der nächste Schritt besteht darin, Ihre Notfall Standorte hinzuzufügen. Weitere Informationen finden Sie unter [hinzufügen, ändern oder Entfernen eines Notfall Standorts für Ihre Organisation](add-change-remove-emergency-location-organization.md).
    
    > [!IMPORTANT]
    > Zum Überprüfen einer Straßen-oder bürgerlichen Adresse müssen Sie sicherstellen, dass Sie legitim und ordnungsgemäß formatiert ist. Es ist möglich, dass eine teilweise korrekte Notfalladresse, beispielsweise ein falsch eingegebener Name des Orts, weiterhin die Validierung durchlaufen kann. Der Überprüfungsprozess verwendet alle Teile einer bestimmten Adresse, um festzustellen, ob er genügend Informationen enthält, um den Anruf an das entsprechende Notfall-Dispatch-Center weiterzuleiten. Wenn dies der Fall ist, wird Sie als validiert zurückgegeben und kann dann einer Telefonnummer zugewiesen werden.
  
3. **Holen Sie sich Telefonnummern**. Der nächste Schritt besteht darin, Telefonnummern für Ihre Benutzer zu erhalten. Sie können dies tun, indem Sie neue Telefonnummern von Office 365 oder durch "portieren" oder übertragen Ihrer vorhandenen Telefonnummern auf Office 365. Die vollständigen Schritte finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Zuweisen von Telefonnummern** Der letzte Schritt besteht darin, es Benutzern zu ermöglichen, Telefonanrufe zu tätigen und zu empfangen. Dazu müssen Sie jedem Benutzer eine Telefonnummer zuweisen. Informationen zum Zuweisen einer Telefonnummer finden Sie unter [zuweisen, ändern oder Entfernen einer Telefonnummer für einen Benutzer](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Wenn Sie weitere Telefonnummern erhalten möchten, [wenden Sie sich an den PSTN-Service-Desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

    
## <a name="related-topics"></a>Verwandte Themen

[Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)
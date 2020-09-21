---
title: Blockieren des Zugriffs auf SharePoint für bestimmte Benutzer
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen zum Blockieren des Zugriffs auf SharePoint für bestimmte Benutzer
ms.openlocfilehash: a2cfdb938dc11d38303df59061db1c46e5b08fcc
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135929"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>Blockieren des Zugriffs auf SharePoint für bestimmte Benutzer

Das Anwenden einer beliebigen Richtlinie für den bedingten Zugriff auf SharePoint in Microsoft 365 wird auch für Teams übernommen. Einige Organisationen möchten jedoch den Zugriff auf SharePoint-Dateien blockieren (hochladen, herunterladen, anzeigen, bearbeiten, erstellen), aber ihren Mitarbeitern die Verwendung von Desktop-, Mobil-und Webclients von Teams auf nicht verwalteten Geräten ermöglichen. Unter den Richtlinien für die Zertifizierungsstelle würde das Blockieren von SharePoint auch dazu führen, dass Teams blockiert werden. In diesem Artikel wird erläutert, wie Sie diese Einschränkung umgehen und ihren Mitarbeitern ermöglichen, weiterhin Teams zu verwenden, während der Zugriff auf in SharePoint gespeicherte Dateien vollständig blockiert wird.

> [!Note]
> Das Blockieren oder Einschränken des Zugriffs auf nicht verwalteten Geräten basiert auf Azure AD-bedingten Zugriffsrichtlinien. Informationen zur [Azure AD-Lizenzierung](https://azure.microsoft.com/pricing/details/active-directory/). Eine Übersicht über den bedingten Zugriff in Azure AD finden Sie unter [bedingter Zugriff in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Informationen zu empfohlenen SharePoint Online-Zugriffsrichtlinien finden Sie unter [Richtlinien Empfehlungen zum Sichern von SharePoint-Websites und-Dateien](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies). Wenn Sie den Zugriff auf nicht verwalteten Geräten einschränken, müssen Benutzer auf verwalteten Geräten eine der [unterstützten Betriebssystem-und Browser Kombinationen](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)verwenden, oder Sie haben auch eingeschränkten Zugriff.

Sie können den Zugriff sperren oder einschränken für:

- Benutzer in der Organisation oder nur einige Benutzer oder Sicherheitsgruppen.

- Alle Websites in der Organisation oder nur einige Websites.

Wenn Access blockiert ist, wird eine Fehlermeldung angezeigt. Das Blockieren des Zugriffs hilft, Sicherheit zu gewährleisten und sichere Daten zu schützen. Wenn Access blockiert ist, wird eine Fehlermeldung angezeigt.

1. Öffnen Sie das SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).

2. Erweitern Sie **Richtlinien**  >  **Zugriffsrichtlinien**.

3. Wählen Sie im Abschnitt **nicht verwaltete Geräte** die Option **Zugriff blockieren** aus, und wählen Sie **Speichern**aus.

   ![Abschnitt "nicht verwaltete Geräte" für Richtlinien](media/no-sharepoint-access1.png)

4. Öffnen Sie das [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) -Portal, und navigieren Sie zu den **Richtlinien für den bedingten Zugriff**.

    Sie werden sehen, dass eine neue Richtlinie von SharePoint erstellt wurde, die mit diesem Beispiel vergleichbar ist:

    ![eine neue Richtlinie mit dem Namen use app-erzwungene Einschränkungen für den Browser Zugriff](media/no-sharepoint-access2.png)

5. Aktualisieren Sie die Richtlinie so, dass nur bestimmte Benutzer oder eine Gruppe darauf ausgerichtet sind.

    ![das SharePoint Admin Center mit hervorgehobenem Abschnitt "Benutzer auswählen"](media/no-sharepoint-access2b.png)

  > [!Note]
> Durch das Festlegen dieser Richtlinie wird der Zugriff auf das SharePoint-Verwaltungsportal reduziert. Wir empfehlen, dass Sie die Ausschlussrichtlinie konfigurieren und die globalen und SharePoint-Administratoren auswählen.

6. Überprüfen, ob nur SharePoint als gezielte Cloud-App ausgewählt ist

    ![SharePoint ist als Ziel-App ausgewählt.](media/no-sharepoint-access3.png)

7. Aktualisieren Sie die **Bedingungen** auch, um Desktop Clients einzubeziehen.

    ![Desktop-und Mobile Apps hervorgehoben.](media/no-sharepoint-access4.png)

8. Sicherstellen, dass **Grant Access** aktiviert ist

    ![Grant Access ist aktiviert.](media/no-sharepoint-access5.png)

9. Stellen Sie sicher, dass die Anwendung **erzwungene Einschränkungen verwenden** aktiviert ist.

10. Aktivieren Sie Ihre Richtlinie, und wählen Sie **Speichern**aus.

    ![Die erzwungenen App-Einschränkungen sind aktiviert.](media/no-sharepoint-access6.png)

Um Ihre Richtlinie zu testen, müssen Sie sich von jedem Client wie der Team-Desktop-App oder dem OneDrive for Business-synchronisierungsclient abmelden und sich erneut anmelden, um die Richtlinie zu sehen. Wenn Ihr Zugriff blockiert wurde, wird in Teams eine Meldung angezeigt, die besagt, dass das Element möglicherweise nicht vorhanden ist.

 ![Nachricht "Element nicht gefunden"](media/access-denied-sharepoint.png)

In SharePoint erhalten Sie eine Nachricht vom Zugriff verweigert.

![Die Meldung "Zugriff verweigert".](media/blocked-access-warning.png)

## <a name="related-topics"></a>Verwandte Themen

[Steuern des Zugriffs auf nicht verwaltete Geräte in SharePoint](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

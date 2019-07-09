---
title: Informationsbarrieren in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/08/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: Informieren Sie sich über Informationsbarrieren und ihre Auswirkungen auf Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a739130c399012e49522dcf3f88473fb6f85e5c
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588127"
---
# <a name="information-barriers-in-microsoft-teams"></a>Informationsbarrieren in Microsoft Teams

Informationsbarrieren sind Richtlinien, die ein Administrator konfigurieren kann, um zu verhindern, dass Einzelpersonen oder Gruppen miteinander kommunizieren. Dies ist hilfreich, wenn beispielsweise eine Abteilung Informationen verarbeitet, die nicht für andere Abteilungen freigegeben werden sollen, oder eine Gruppe verhindert oder isoliert werden muss, um mit Personen außerhalb dieser Gruppe zu kommunizieren.

> [!NOTE]
> - Gruppen für Informationsbarrieren können nicht für Mandanten erstellt werden.
> - Die Verwendung von Bots zum Hinzufügen von Benutzern wird in Version 1 nicht unterstützt.
> - Informationsbarrieren Version 1 enthält keine Unterstützung für SharePoint und OneDrive for Business. Wir arbeiten daran, das Feature in SharePoint zu aktivieren und kommunizieren, sobald es verfügbar ist.

Richtlinien für Informationsbarrieren verhindern auch Nachschlagevorgänge und Ermittlungen. Wenn Sie versuchen, mit einer Person zu kommunizieren, mit der Sie nicht kommunizieren sollten, wird dieser Benutzer in der Personenauswahl nicht gefunden.

## <a name="background"></a>Hintergrund

Der wichtigste Treiber für Informationsbarrieren ist die Finanzdienstleistungsbranche. Die Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) überprüft Informationsbarrieren und Interessenkonflikte innerhalb von Mitgliedsunternehmen und bietet Anleitungen für die Verwaltung solcher Konflikte (FINRA 2241, [Debt Research Regulation Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>Wann sollte ich Informationsbarrieren verwenden?

Möglicherweise möchten Sie Informationsbarrieren in Situationen wie den folgenden verwenden:

- Ein Team muss daran gehindert werden, Daten mit einem bestimmten anderen Team zu kommunizieren oder zu teilen.
- Ein Team darf keine Daten an Personen außerhalb des Teams weitergeben oder freigeben.

Der Evaluierungs Dienst für Informations Barriere-Richtlinien bestimmt, ob eine Kommunikation den Richtlinien für Informationsbarrieren entspricht. 

## <a name="managing-information-barrier-policies"></a>Verwalten von Richtlinien für Informationsbarrieren

Richtlinien für Informationsbarrieren werden im Office 365 Security #a0 Compliance Center (SCC) mithilfe von PowerShell-Cmdlets verwaltet. Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Bevor Sie Richtlinien einrichten oder definieren, **müssen Sie die Bereichs Verzeichnissuche in Microsoft Teams aktivieren**. Warten Sie mindestens 24 Stunden nach der Aktivierung der Bereichs Verzeichnissuche, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren. [Informieren Sie sich über die Voraussetzungen für Informationsbarrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Administratorrolle für Informationsbarrieren

Die IB-Compliance-Verwaltungsrolle ist für die Verwaltung von Richtlinien für Informationsbarrieren verantwortlich. Weitere Informationen zu dieser Rolle finden Sie unter [Berechtigungen im Office 365 Security #a0 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="when-are-information-barrier-policies-checked"></a>Wann werden die Richtlinien für Informationsbarrieren überprüft?

Richtlinien für Informationsbarrieren werden überprüft, wenn die folgenden Teams-Ereignisse stattfinden:

- **Mitglieder werden einem Team hinzugefügt** – Wenn Sie einen Benutzer zu einem Team hinzufügen, muss die Richtlinie des Benutzers mit den Richtlinien für Informationsbarrieren anderer Teammitglieder ausgewertet werden. Nachdem der Benutzer erfolgreich hinzugefügt wurde, kann der Benutzer alle Funktionen im Team ohne weitere Überprüfungen ausführen. Wenn die Richtlinie des Benutzers blockiert, dass Sie dem Team hinzugefügt wird, wird der Benutzer nicht in der Suche angezeigt.
- **Ein neuer Chat wird angefordert** – jedes Mal, wenn ein neuer Chat zwischen zwei oder mehr Benutzern angefordert wird, wird der Chat ausgewertet, um sicherzustellen, dass er keine Richtlinien für Informationsbarrieren verletzt. Wenn die Unterhaltung gegen eine Richtlinie für Informationsbarrieren verstößt, wird die Unterhaltung nicht initiiert.
- **Ein Benutzer ist eingeladen, an einer Besprechung teilzunehmen** – wenn ein Benutzer zur Teilnahme an einer Besprechung eingeladen wird, wird die Richtlinie des Benutzers anhand der Richtlinien anderer Teammitglieder ausgewertet, und wenn ein Verstoß vorliegt, ist der Benutzer nicht berechtigt, an der Besprechung teilzunehmen.
- **Ein Bildschirm wird von zwei oder mehr Benutzern freigegeben** – jedes Mal, wenn ein Bildschirm von zwei oder mehr Benutzern freigegeben wird, muss die Bildschirmfreigabe ausgewertet werden, um sicherzustellen, dass Sie die Richtlinien anderer Benutzer für Informationsbarrieren nicht verletzt. Wenn eine Richtlinie für Informationsbarrieren verletzt wird, ist die Bildschirmfreigabe nicht zulässig.
- **Ein Benutzer platziert einen Telefonanruf (VoIP) in Teams** – wenn ein Sprachanruf von einem Benutzer an einen anderen Benutzer oder eine Gruppe von Benutzern initiiert wird, wird der Anruf ausgewertet, um sicherzustellen, dass er die Richtlinien anderer Teammitglieder gegen die Informations Barriere nicht verletzt. Bei Verstößen ist der Sprachanruf blockiert.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>Was passiert mit vorhandenen Chat-Threads, wenn eine Richtlinie geändert wird?

Wenn der Administrator der Informations Barriere-Richtlinie Änderungen an einer Richtlinie vornimmt oder eine Richtlinienänderung aufgrund einer Änderung des Profils eines Benutzers (beispielsweise bei einer Auftragsänderung oder einem ähnlichen Grund) in Kraft tritt, wird der Evaluierungs Dienst für Informations Barriere-Richtlinien automatisch durchsucht die Mitglieder, um sicherzustellen, dass Mitglieder des Teams keine Richtlinien verletzen.

Wenn ein Chat oder eine andere Kommunikation zwischen Benutzern vorhanden ist, eine neue Richtlinie festgesetzt oder eine vorhandene Richtlinie geändert wird, wertet der Dienst vorhandene Kommunikation aus, um sicherzustellen, dass die Kommunikation weiterhin zulässig ist. 

- **1:1-Chat** – wenn die Kommunikation zwischen den beiden Benutzern nicht mehr zulässig ist (wenn eine Richtlinie, die die Kommunikation blockiert, auf einen oder beide Benutzer angewendet wird), wird die weitere Kommunikation blockiert, und die Chat Unterhaltung wird schreibgeschützt.
- **Gruppen-Chat** – wenn die Kommunikation von einem Benutzer zur Gruppe nicht mehr zulässig ist (Wenn beispielsweise ein Benutzer den Arbeitsplatz wechselt), kann der Benutzer zusammen mit den anderen Benutzern, die gegen die Richtlinie verstoßen, aus dem Gruppen-Chat entfernt werden, und die weitere Kommunikation mit der Gruppe wird nicht zulässig. Der Benutzer kann weiterhin alte Konversationen sehen (die schreibgeschützt sind), aber nicht in der Lage sein, neue Konversationen mit der Gruppe zu sehen oder daran teilzunehmen. Wenn die neue oder geänderte Richtlinie, die die Kommunikation verhindert, auf mehr als einen Benutzer angewendet wird, werden die Benutzer, die von der Richtlinie betroffen sind, möglicherweise aus dem Gruppen-Chat entfernt. Sie können weiterhin alte Konversationen sehen. 
- **Team** – alle Benutzer, die aus der Gruppe entfernt wurden, werden aus dem Team entfernt und können keine vorhandenen oder neuen Konversationen anzeigen oder daran teilnehmen.

## <a name="what-will-users-experience-if-another-user-is-blocked"></a>Was können Benutzer erleben, wenn ein anderer Benutzer blockiert ist?

Derzeit erfahren Benutzer Folgendes, wenn eine Richtlinie für Informationsbarrieren einen anderen Benutzer blockiert:

- **Registerkarte "Personen"** : ein Benutzer kann einige blockierte Benutzer auf der Registerkarte " **Personen** " sehen. Der Benutzer kann die blockierten Benutzer auswählen.
- **Registerkarte "Aktivität"** – wenn ein Benutzer die Registerkarte " **Aktivität** " eines blockierten Benutzers besucht, werden keine Beiträge angezeigt. (Auf der Registerkarte **Aktivität** werden nur Kanal Beiträge angezeigt, und es gibt keine gemeinsamen Kanäle zwischen den beiden Benutzern.)
- **Organigramme** : Wenn ein Benutzer auf ein Organigramm zugreift, auf dem ein blockierter Benutzer angezeigt wird, sieht der Benutzer den blockierten Benutzer im Diagramm und kann auf Aktionen im Diagramm klicken, aber die Aktionen (wie Anrufe) werden nicht durchlaufen.
- **Personen Karte** : Wenn ein Benutzer an einer Unterhaltung teilnimmt und anschließend blockiert wird, können andere Benutzer weiterhin die Personen Karte für den blockierten Benutzer sehen. Alle auf der Karte aufgelisteten Aktionen (wie Anrufe und Chats) stehen zur Verfügung, aber die Aktionen werden nicht durchlaufen.
- **Vorgeschlagene Kontakte** – in der Liste der vorgeschlagenen Kontakte (die erste Kontaktliste, die für neue Benutzer angezeigt wird) können Benutzer alle vorgeschlagenen Kontakte (einschließlich blockierter Benutzer) sehen. Wenn ein Benutzer jedoch auf den Namen eines blockierten Benutzers klickt, um den Chatbereich zu öffnen, wird die Nachricht blockiert.
- **Chat-Kontakte** – ein Nutzer kann blockierte Nutzer in der Chat-Kontaktliste sehen.
- **Anrufe an Kontakte** – ein Benutzer kann blockierte Benutzer in der Kontaktliste für Anrufe sehen und Aktionen wie Anrufe und Nachrichten werden angezeigt, aber wenn der Benutzer versucht, einen Anruf zu tätigen oder eine Nachricht an den blockierten Nutzer zu senden, wird der Anruf oder die Nachricht nicht durchlaufen.
- **Migration von Skype zu Teams** – während einer Migration von Skype for Business zu Teams werden alle Benutzer, auch solche, die durch Richtlinien für Informationsbarrieren blockiert sind, in Teams migriert und dann wie oben beschrieben gehandhabt.

In Kürze: Benutzer erfahren Folgendes, wenn eine Richtlinie für Informationsbarrieren einen anderen Benutzer blockiert:

- **Registerkarte "Personen"** – Benutzer können auf der Registerkarte **Personen** keine blockierten Benutzer sehen.
- **Registerkarte "Aktivität"** – wenn ein Benutzer die Registerkarte " **Aktivität** " eines blockierten Benutzers besucht, werden keine Beiträge angezeigt. (Auf der Registerkarte **Aktivität** werden nur Kanal Beiträge angezeigt, und es gibt keine gemeinsamen Kanäle zwischen den beiden Benutzern.)
- **Organigramme** : Wenn ein Benutzer auf ein Organigramm zugreift, auf dem ein blockierter Benutzer angezeigt wird, wird der blockierte Benutzer im Organigramm nicht angezeigt, und stattdessen wird eine Fehlermeldung angezeigt.
- **Personen Karte** : Wenn ein Benutzer an einer Unterhaltung teilnimmt und der Benutzer anschließend blockiert wird, werden anderen Benutzern anstelle der Personen Karte eine Fehlermeldung angezeigt, wenn Sie den Mauszeiger über den Namen des blockierten Benutzers bewegen. Auf der Karte aufgelistete Aktionen (wie Anrufe und Chats) sind nicht verfügbar.
- **Vorgeschlagene Kontakte** – blockierte Benutzer werden nicht in der Liste der vorgeschlagenen Kontakte angezeigt (die erste Kontaktliste, die für neue Benutzer angezeigt wird).
- **Chat-Kontakte** – ein Nutzer kann in der Chat-Kontaktliste nicht blockierte Nutzer sehen.
- **Anrufe an Kontakte** : ein Benutzer kann blockierte Benutzer in der Anruf Kontaktliste sehen, die blockierten Benutzer werden jedoch identifiziert, und die einzige Aktion, die der Benutzer ausführen kann, besteht darin, diese zu löschen.
- **Migration von Skype zu Teams** – während einer Migration von Skype for Business zu Teams werden alle Benutzer, auch solche, die durch Richtlinien für Informationsbarrieren blockiert sind, in Teams migriert und dann wie oben beschrieben gehandhabt.

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Informationsbarrieren werden jetzt eingeführt und sind in Abonnements enthalten, wie beispielsweise:

- Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Compliance
- Microsoft 365 E5-Kompatibilität

Weitere Informationen, einschließlich Pläne und Preise, finden Sie unter [Compliance-Lösungen](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).

## <a name="more-information"></a>Weitere Informationen

- Wenn Sie mehr über Informationsbarrieren erfahren möchten, lesen Sie [Informationen](https://docs.microsoft.com/office365/securitycompliance/information-barriers)zu Barrieren.

- Informationen zum Einrichten von Richtlinien für Informationsbarrieren finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Informationen zum Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren finden Sie unter [Bearbeiten (oder entfernen) von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-edit-segments-policies.md)
---
title: Teams erleben in einer Microsoft 365 Multi-Geo-fähigen Umgebung
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: In diesem Artikel erfahren Sie mehr über die Verwendung von Teams in einer Microsoft 365 Multi-Geo-fähigen Umgebung.
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757750"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams in einer Microsoft 365 Multi-Geo-fähigen Mandanten Erfahrung

Microsoft Teams ist eine Gruppen-Chat-Software, der Hub für Teamarbeit in Microsoft 365. Sie wird vom Microsoft 365 Groups-Dienst zusammen mit SharePoint und OneDrive für die Dateinutzung unterstützt. In einer Multi-Geo-Organisation, in der der Mandant auf viele geografische Standorte wie Nordamerika, Europa und Australien ausgedehnt wird, ist die Erfahrung der zugrunde liegenden Dateien Multi-Geo-bewusst, sodass die Team Erfahrung mit der Datei Zusammenarbeit auch Multi-Geo-fähig ist. Auf diese Weise können Teams Dateien an verschiedenen geografischen Standorten in der systemeigenen Datei Oberfläche übertragen.

In einer contoso-Mietdauer mit Europa als Satelliten Geo und Nordamerika als zentrales Geo sieht ein europäischer Satelliten Benutzer beispielsweise seine OneDrive-Dateien im linken Bereich unter der Registerkarte "Dateien", obwohl die Dateien in der Europa-Datenposition gehostet werden und die Vereinigten Staaten der zentrale Standort des Mandanten sind. Darüber hinaus kann der Benutzer auf die zuletzt verwendeten Dateien unter dem Blade für zuletzt verwendete Ansichten zugreifen. Aktuelle Dateien können Dateien umfassen, die von Benutzern in anderen Geo-Speicherorten freigegeben wurden. 

Die SharePoint-Website eines bestimmten Teams ist auch Multi-Geo-fähig. Das heißt, wenn ein europäischer Satelliten Benutzer ein Team erstellt, wird die entsprechende SharePoint-Website am Standort Europa erstellt, und die Dateien, die diesem Team zugeordnet sind, werden an diesem Speicherort beibehalten. Alle nachfolgenden Erfahrungen, beispielsweise das Hochladen einer neuen Datei oder das Bearbeiten der Datei, werden an diesem europäischen Standort gespeichert, wobei das Versprechen einer Datenspeicherung für diese Dateien bleibt.

Beachten Sie, dass Unterhaltungen in Chats und Besprechungsnotizen innerhalb der Teams nicht multigeo-fähig sind und nur innerhalb des zentralen Standorts der Organisation aufbewahrt werden.

Weitere Informationen zu Multi-Geo finden Sie unter [Microsoft Multi-Geo-Funktionen](https://aka.ms/multi-geo).

---
title: Informationen für IT-Administratoren zum Microsoft Teams-RealWear-Client (Vorschau)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Eine Erläuterung des RealWear-Clients für Microsoft Teams für IT-Administratoren.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95d3ead9c85fc58fdc55cd321e55b0ff9ca76853
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102389"
---
# <a name="realwear-for-microsoft-teams"></a>RealWear für Microsoft Teams

> [!NOTE]
> Dies ist eine Vorschauversion oder eine Vorabfunktion.

Dieser Artikel befasst sich mit dem Microsoft Teams-Client für am Kopf getragene RealWear-Geräte. Mitarbeiter mit RealWear HMT-1 und HMT-1Z1 können nun über einen Videoanruf in Teams mit einem Remoteexperten zusammenarbeiten. Mithilfe einer sprachgesteuerten Benutzeroberfläche ermöglicht Teams für RealWear, dass Außendienstmitarbeiter die Hände jederzeit frei haben, während das Lagebewusstsein in lauten und gefährlichen Umgebungen aufrechterhalten wird. Indem sie in Echtzeit zeigen, was sie sehen, können Außendienstmitarbeiter die Zeit zur Lösung von Problemen zu verkürzen und das Risiko eines teuren Ausfalls reduzieren.

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a>Wie man Microsoft Teams für RealWear einsetzt

Der Microsoft Teams-Client für RealWear befindet sich derzeit in der Public Preview. Um an dieser Vorschau teilzunehmen, benötigen Sie Folgendes:

RealWear-Geräte, die auf Version 10.5.0 oder höher aktualisiert wurden. Weitere Informationen finden Sie [hier](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).

> [!IMPORTANT]
> Registrieren Sie sich [hier](https://www.realwear.com/solutions/microsoft-teams/#C1) für den Zugriff auf den Teams für RealWear-Client in [RealWear Foresight](https://cloud.realwear.com/).

## <a name="required-licenses"></a>Erforderliche Lizenzen

Microsoft Teams-Lizenzen sind Bestandteil von Office 365-Abonnements. Für die Nutzung von Teams für RealWear sind keine weiteren Lizenzen erforderlich. Weitere Informationen zum Erhalten von Teams finden Sie unter [Wie erhalte ich Zugriff auf Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).

## <a name="managing-realwear-devices"></a>Verwalten von RealWear-Geräten

### <a name="microsoft-endpoint-manager"></a>Microsoft Endpunkt-Manager

RealWear-Geräte können über den Modus „Android-Geräteadministrator“ verwaltet werden. Die Unterstützung für die Verwaltung über Android Enterprise ist begrenzt, da auf den Geräten derzeit keine Google Mobile-Dienste (GMS) zur Verfügung stehen.

- Weitere Informationen zum Verwalten von RealWear-Geräten in Microsoft Endpoint Manager finden Sie unter [Registrierung von Android-Geräteadministratoren in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).

### <a name="third-party-enterprise-mobility-managers-emms"></a>Drittanbieter für Enterprise Mobility-Manager (EMMs)

Anleitungen zu EMMs von Drittanbietern finden Sie unter [Unterstützte Enterprise Mobility-Verwaltungsanbieter](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).

---
title: Konfigurieren der Hybridkonnektivität | Bereitstellen von Skype for Business Server 2019 Connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Implementieren der Hybridkonnektivität zwischen Skype for Business Server und Teams.
ms.openlocfilehash: 67caabe77afb9f06dcf28f47a93f8eef06c08de8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624567"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Hybridkonnektivität zwischen Skype for Business Server und Teams konfigurieren.  Die Hybridkonnektivität ermöglicht es Ihnen, Ihre lokalen Benutzer auf Teams zu verschieben, und ihre Benutzer können cloudbasierte Dienste nutzen.
  
Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie die Planung der [Hybridkonnektivität zwischen Skype for Business Server und Teams](plan-hybrid-connectivity.md)gelesen haben.
  
In der folgenden Tabelle sind die aufgaben aufgeführt, die zum Konfigurieren Skype for Business Hybridkonnektivität erforderlich sind, und links zu den zugehörigen Artikeln für weitere Informationen.
  
|Schritt|Beschreibung|
|:-----|:-----|
|Erstellen eines Mandantenkontos für Microsoft 365   <br/> |Erfahren Sie mehr über Microsoft 365 unter [Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=254980)  <br/> Um sicherzustellen, dass Ihre Umgebung für Microsoft 365 bereit ist, lesen Sie die [Systemanforderungen.](https://products.office.com/office-system-requirements)  <br/> Ausführliche Informationen zum Einrichten von Microsoft 365 finden Sie unter [Erste Schritte mit Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Hinzufügen Ihrer Domäne zu Ihrer Microsoft 365 Organisation und Überprüfen des Besitzes  <br/> | Sie müssen Ihre Domäne zu Ihrer Microsoft 365 Organisation hinzufügen und dann die Schritte ausführen, um die Domäne mit Microsoft 365 zu überprüfen. Dies dient zur Bestätigung, dass Sie der Besitzer der Domäne sind. <br/> Um Ihre Domäne zu Ihrer Microsoft 365 Organisation hinzuzufügen, führen Sie die unter [Hinzufügen einer Domäne zu Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)beschriebenen Schritte aus.  <br/> |
|Einrichten der Active Directory-Synchronisierung  <br/> |Die Active Directory-Synchronisierung hält Ihr lokales Active Directory kontinuierlich mit Microsoft 365 synchronisiert. Auf diese Weise können Sie synchronisierte Versionen jedes Benutzerkontos und jeder Gruppe erstellen.  <br/> <br> **Wichtig:** Sie müssen die AD-Konten für alle Skype for Business Benutzer in Ihrer Organisation zwischen Ihren lokalen und Onlinebereitstellungen synchronisieren, auch wenn Benutzer nicht zu Teams verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrer Organisation möglicherweise nicht wie erwartet. Weitere Informationen finden Sie unter [Konfigurieren von Azure AD-Verbinden für Hybridumgebungen.](configure-azure-ad-connect.md)         |
| Konfigurieren der Hybridbereitstellung von Skype for Business | Es gibt drei grundlegende Schritte: <br><br> 1. Konfigurieren Sie Ihre lokale Umgebung so, dass sie mit Microsoft 365 verbunden wird. <br> 2. Konfigurieren Sie Ihre lokale Umgebung so, dass sie Microsoft 365 vertraut und den freigegebenen SIP-Adressraum mit Microsoft 365 aktiviert.<br> 3. Aktivieren Sie den freigegebenen SIP-Adressraum in Ihrer Microsoft 365 Organisation. <br><br> Wenn Sie Exchange lokal haben, können Sie OAuth zwischen Ihren Exchange lokalen und Onlineumgebungen konfigurieren. <br> <br>Weitere Informationen finden Sie unter [Konfigurieren Skype for Business Hybrid.](configure-federation-with-skype-for-business-online.md)
|Verschieben von Pilotbenutzern  <br/> |Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren Ihrer Umgebung für Teams abgeschlossen haben, können Sie mit dem Verschieben von Pilotbenutzern in Ihre Online-Microsoft 365 Organisation beginnen. Weitere Informationen finden Sie unter [Verschieben von Benutzern aus der lokalen Umgebung in Teams](move-users-from-on-premises-to-Teams.md).  <br/> |

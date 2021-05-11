---
title: Konfigurieren von hybriden | Bereitstellen Skype for Business Server 2019 connect
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Implementieren der Hybridkonnektivität zwischen Skype for Business Server und Teams.
ms.openlocfilehash: 1b1fee4fe513778433bff077ce23973e4bfc0d8a
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305939"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Teams

**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie hybride Verbindungen zwischen Skype for Business Server und Teams (oder Skype for Business Online bis zur Rente) konfigurieren.  Mit hybrider Konnektivität können Sie Ihre lokalen Benutzer nach Teams (oder Skype for Business Online) verschieben und Ihre Benutzer clouddienste nutzen.
  
Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie planen der Hybridkonnektivität zwischen Skype for Business Server [und Teams](plan-hybrid-connectivity.md).
  
In der folgenden Tabelle sind die Aufgaben aufgeführt, die zum Konfigurieren Skype for Business Hybridkonnektivität erforderlich sind, und enthält Links zu den zugeordneten Artikeln, um weitere Informationen zu erhalten.
  
|Schritt|Beschreibung|
|:-----|:-----|
|Erstellen eines Mandantenkontos für Microsoft 365   <br/> |Weitere Informationen zu Microsoft 365 finden Sie [unter Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Informationen zum Sicherstellen, dass Ihre Umgebung für die Microsoft 365 ist, finden Sie unter [System Requirements](https://products.office.com/office-system-requirements).  <br/> Weitere Informationen zum Einrichten von Microsoft 365 finden Sie unter [Erste Schritte mit Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Hinzufügen Ihrer Domäne zu Microsoft 365 Organisation und Überprüfen des Besitzes  <br/> | Sie müssen Ihre Domäne ihrer organisation Microsoft 365 hinzufügen und dann die Schritte ausführen, um die Domäne mit Microsoft 365. Dadurch wird bestätigt, dass Sie der Besitzer der Domäne sind. <br/> Führen Sie die unter Hinzufügen einer Domäne zu Microsoft 365 [beschriebenen](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)Schritte aus, um Ihre Domäne Microsoft 365.  <br/> |
|Einrichten der Active Directory-Synchronisierung  <br/> |Die Active Directory-Synchronisierung sorgt dafür, dass Ihr lokales Active Directory kontinuierlich mit Microsoft 365. Auf diese Weise können Sie synchronisierte Versionen der einzelnen Benutzerkonten und Gruppen erstellen.  <br/> <br> **Wichtig:** Sie müssen die AD-Konten für alle Skype for Business-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Onlinebereitstellungen synchronisieren, auch wenn Benutzer nicht zu Teams (oder Skype for Business Online) verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrer Organisation möglicherweise nicht wie erwartet. Weitere Informationen finden Sie unter [Configure Azure AD Verbinden for hybrid environments](configure-azure-ad-connect.md).         |
| Konfigurieren der Hybridbereitstellung von Skype for Business | Es gibt drei grundlegende Schritte: <br><br> 1. Konfigurieren Sie Ihre lokale Umgebung so, dass sie eine Verbindung mit Microsoft 365. <br> 2. Konfigurieren Sie Ihre lokale Umgebung so, dass Microsoft 365 und freigegebener SIP-Adressraum mit Microsoft 365.<br> 3. Aktivieren Sie freigegebenen SIP-Adressraum in Microsoft 365 Organisation. <br><br> Wenn Sie Exchange lokal verwenden, möchten Sie möglicherweise auch OAuth zwischen den lokalen Exchange- und Skype for Business Online-Umgebungen konfigurieren. <br> <br>Weitere Informationen finden Sie unter [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).
|Verschieben von Pilotbenutzern  <br/> |Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren Ihrer Umgebung für Teams (oder Skype for Business Online) abgeschlossen haben, können Sie damit beginnen, Pilotbenutzer in Ihre Microsoft 365 zu verschieben. Weitere Informationen finden Sie unter [Move users from on premises to Teams](move-users-from-on-premises-to-Teams.md) and Move users from on premises to Skype for Business [Online](move-users-from-on-premises-to-skype-for-business-online.md).  <br/> |

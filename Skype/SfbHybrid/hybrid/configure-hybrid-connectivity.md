---
title: Konfigurieren der hybriden Konnektivität | Bereitstellen von Skype for Business Server 2019 Connect
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
ms.openlocfilehash: fee7587c641f2fd55cd8b4ac4da72b3944b819a1
ms.sourcegitcommit: 64b9f7297d33a883506893fb68d1ad5202b4df1a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2021
ms.locfileid: "59682810"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Hybridkonnektivität zwischen Skype for Business Server und Teams konfigurieren.  Die Hybridkonnektivität ermöglicht es Ihnen, Ihre lokalen Benutzer in Teams zu verschieben, und ermöglicht Es Ihren Benutzern, cloudbasierte Dienste zu nutzen.
  
Bevor Sie die Schritte in diesem Thema ausführen, sollten Sie die Planung der [Hybridkonnektivität zwischen Skype for Business Server und Teams gelesen](plan-hybrid-connectivity.md)haben.
  
In der folgenden Tabelle sind die aufgaben aufgeführt, die zum Konfigurieren Skype for Business Hybridkonnektivität erforderlich sind, und links zu den zugehörigen Artikeln für weitere Informationen.
  
|Schritt|Beschreibung|
|:-----|:-----|
|Erstellen Sie ein Mandantenkonto für Microsoft 365.   <br/> |Erfahren Sie mehr über Microsoft 365 unter [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980).  <br/> Um sicherzustellen, dass Ihre Umgebung bereit für Microsoft 365 ist, lesen Sie die [Systemanforderungen.](https://products.office.com/office-system-requirements)  <br/> Ausführliche Informationen zum Einrichten von Microsoft 365 finden Sie unter [Erste Schritte mit Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982).  <br/> |
|Fügen Sie Ihre Domäne zu Ihrer Microsoft 365 Organisation hinzu, und überprüfen Sie den Besitz.  <br/> | Sie müssen Ihre Domäne zu Ihrer Microsoft 365 Organisation hinzufügen und dann die Schritte ausführen, um die Domäne mit Microsoft 365 zu überprüfen. Diese Überprüfung dient zur Bestätigung, dass Sie der Besitzer der Domäne sind. <br/> Um Ihre Domäne zu Ihrer Microsoft 365 Organisation hinzuzufügen, führen Sie die unter [Hinzufügen einer Domäne zu Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)beschriebenen Schritte aus. Lesen Sie unbedingt die nachstehenden Anleitungen zu [DNS-Auswirkungen auf Organisationen, die hybrid werden.](#dns-implications-for-on-premises-organizations-that-become-hybrid) <br/> |
|Einrichten der Active Directory-Synchronisierung.  <br/> |Die Active Directory-Synchronisierung stellt sicher, dass Ihr lokales Active Directory kontinuierlich mit Microsoft 365 synchronisiert wird, sodass Sie synchronisierte Versionen jedes Benutzerkontos und jeder Gruppe erstellen.  <br/> <br> **Wichtig:** Sie müssen die Active Directory-Konten für alle Skype for Business Benutzer in Ihrer Organisation zwischen Ihren lokalen und Onlinebereitstellungen synchronisieren, auch wenn Benutzer nicht zu Teams verschoben werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrer Organisation möglicherweise nicht wie erwartet. Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Verbinden für Hybridumgebungen.](configure-azure-ad-connect.md)         |
| Konfigurieren der Hybridbereitstellung von Skype for Business | Es gibt drei grundlegende Schritte: <br><br> 1. Konfigurieren Sie Ihre lokale Umgebung so, dass sie mit Microsoft 365 verbunden wird. <br> 2. Konfigurieren Sie Ihre lokale Umgebung so, dass sie Microsoft 365 vertraut und den freigegebenen SIP-Adressraum mit Microsoft 365 aktiviert.<br> 3. Aktivieren Sie den freigegebenen SIP-Adressraum in Ihrer Microsoft 365 Organisation. <br><br> Wenn Sie darüber hinaus Exchange lokal haben, sollten Sie OAuth zwischen Ihren Exchange lokalen und Onlineumgebungen konfigurieren. <br> <br>Weitere Informationen finden Sie unter [Konfigurieren Skype for Business Hybrid.](configure-federation-with-skype-for-business-online.md)
|Verschieben von Pilotbenutzern  <br/> |Nachdem Sie die Schritte zum Vorbereiten und Konfigurieren Ihrer Umgebung für Teams abgeschlossen haben, können Sie mit dem Verschieben von Pilotbenutzern zu Ihrer Online-Microsoft 365 Organisation beginnen. Weitere Informationen finden Sie unter [Verschieben von Benutzern aus der lokalen Umgebung in Teams](move-users-from-on-premises-to-Teams.md).  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>DNS-Auswirkungen auf lokale Organisationen, die hybrid werden

Standardmäßig werden Mandanten im TeamsOnly-Modus erstellt. Administratoren können diese Konfiguration nicht ändern. Hybridorganisationen dürfen jedoch nicht im TeamsOnly-Modus sein, da dadurch der Partnerverbund für ihre lokalen Benutzer aufgehoben würde. Teams verfügt über einen integrierten Mechanismus, um sicherzustellen, dass die mandantenweite TeamsOnly-Konfiguration nicht auf neue Hybridmandanten angewendet wird, und dass die mandantenweite TeamsOnly-Konfiguration *aus vorhandenen Mandanten entfernt wird, die hybrid werden.* Dieser Mechanismus basiert auf dem Wert des LyncDiscover-DNS-Eintrags für jede überprüfte Microsoft 365 Domäne (da ein Skype for Business Server lokale Bereitstellung in den meisten Fällen über diesen Eintrag verfügt), wie unten beschrieben.

Wenn ein neues Microsoft 365 Abonnement zum ersten Mal verarbeitet wird, geschieht Folgendes:
- Wenn noch keine überprüften Microsoft 365 Domänen vorhanden sind, wird der Mandant im TeamsOnly-Modus erstellt. Der Wert wird über die TeamsUpgradeOverridePolicy festgelegt, die nur von Microsoft festgelegt werden kann. Wenn der Richtlinienwert "UpgradeToTeams" lautet, hat er Vorrang vor jedem Wert von "TeamsUpgradePolicy".
- Wenn überprüfte Microsoft 365 Domänen vorhanden sind, aber keine öffentlichen DNS LyncDiscover-Einträge erkannt wurden oder wenn alle erkannten LyncDiscover-Einträge alle auf Microsoft 365 (sipfed.online.lync.com, sipfed.online.gov.skypeforbusiness.us usw.) verweisen, wird der Mandant im TeamsOnly-Modus (über TeamsUpgradeOverridePolicy) erstellt.
- Wenn mindestens eine überprüfte Microsoft 365 Domäne vorhanden ist, für die ein LyncDiscover-Datensatz erkannt wird, und dieser Datensatz an einer anderen Stelle als Microsoft 365 zeigt, wird der Mandant im Inselmodus erstellt.

Wenn ein vorhandener Microsoft 365 Mandant erneut bereitgestellt wird (in der Regel aufgrund einer Änderung der überprüften Domänen oder der Abonnementdetails), geschieht Folgendes:
- Wenn ein LyncDiscover-Datensatz für eine oder mehrere der Microsoft 365 überprüften Domänen gefunden wird und dieser Datensatz nicht auf Microsoft 365 verweist, wird der mandantenweite TeamsOnly-Modus (über TeamsUpgradeOverridePolicy) entfernt. Der Mandantenmodus wird auf das zurückgesetzt, was auf Mandantenebene für TeamsUpgradePolicy angegeben ist, bei dem es sich standardmäßig um den Inselmodus handelt.


Es gibt einige Einschränkungen für diesen automatischen Erkennungsmechanismus:
- Wenn Ihre Organisation über keine öffentlichen DNS-Einträge verfügt, wird der TeamsOnly-Modus nicht entfernt, da Microsoft 365 die Einträge nicht erkennen kann. Wenn Ihre Organisation über lokale Skype for Business Server ohne öffentliche DNS-Einträge verfügt, müssen Sie sich an den Microsoft-Support wenden, damit Ihr Mandant heruntergestuft wird.
- Wenn Sie einen öffentlichen DNS-Eintrag zu einer Domäne hinzufügen/aktualisieren, die *bereits* eine Microsoft 365 überprüfte Domäne ist, wird diese DNS-Änderung nicht erkannt, und der TeamsOnly-Modus wird nicht entfernt. Der TeamsOnly-Modus wird nur entfernt, wenn der Mandant erneut bereitgestellt wird. Dies geschieht in der Regel, wenn eine Änderung an Microsoft 365 überprüften Domänen oder am Abonnement erfolgt.  

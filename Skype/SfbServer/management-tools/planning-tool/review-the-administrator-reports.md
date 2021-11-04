---
title: Überprüfen der Administratorberichte in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Die Administratorberichte stellen detaillierte Informationen zu Bereitstellung und Betrieb bereit. Die Berichte werden basierend auf den in "Designwebsites" markierten Auswahlen generiert. Der für den Entwurf verantwortlicher Benutzer kann die Administratorberichte durch Bearbeiten der Netzwerkdiagramme und Definieren der vollständigen IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für Server, Pools und Lastenausgleich ergänzen.
ms.openlocfilehash: e2a30e27b5b1928dacc36e5592033090484f065a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766293"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Überprüfen der Administratorberichte in Skype for Business Server 2015

Die Administratorberichte stellen detaillierte Informationen zu Bereitstellung und Betrieb bereit. Die Berichte werden basierend auf den in **Designwebsites** markierten Auswahlen generiert. Der für den Entwurf verantwortlicher Benutzer kann die Administratorberichte durch Bearbeiten der Netzwerkdiagramme und Definieren der vollständigen IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für Server, Pools und Lastenausgleich ergänzen.

Das Feature "Administratorberichte" ermöglicht Folgendes:

- [Überprüfen des Zusammenfassungsberichts](review-the-administrator-reports.md#Summary_report)

- [Überprüfen des Zertifikatberichts](review-the-administrator-reports.md#Certificates_Report)

- [Überprüfen des Firewallberichts](review-the-administrator-reports.md#Firewall_report)

- [Überprüfen des DNS-Berichts](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Überprüfen des Zusammenfassungsberichts
<a name="Summary_report"> </a>

Der Skype for Business Administratorbericht ist der erste von vier wertvollen Berichten, die Ihren Entwurf detailliert dokumentieren. Die Informationen in diesem Bericht und die anderen drei zugehörigen Berichte sind für Ihre informationstechnologie Teams hilfreich:

![Allgemeiner zusammenfassender Administratorbericht.](../../media/General_Summary_Report_Admin_Report.png)

Der Zusammenfassungsbericht enthält allgemeine Konfigurationsinformationen zu Ihrem Edgenetzwerk. Der Standort, vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) und die IP-Adresse, der Netzwerktyp und kommentare, die für eine bestimmte Rolle spezifisch sind, werden dokumentiert.

Der Designer und jedes der Teams, die die Infrastruktur bereitstellen, verwalten und verwalten, sollten den Zusammenfassungsbericht auf Genauigkeit überprüfen und sicherstellen, dass mindestens Fehler auftreten.

Sie können auch detailliertere Berichte anzeigen:

- Zertifikatbericht

- Firewallbericht

- DNS-Bericht

## <a name="review-the-certificates-report"></a>Überprüfen des Zertifikatberichts
<a name="Certificates_Report"> </a>

Der Zertifikatbericht enthält alle Zertifikate, die in der empfohlenen Skype for Business Server 2015-Bereitstellung erforderlich sind. Das Planungstool erfasst die eingegebenen Antragstellernamen und alternativen Antragstellernamen. Standardtext, der unbearbeitet bleibt, kann eine potenzielle Herausforderung für das Team darstellen, das für das Anfordern und Ausstellen der Zertifikate verantwortlich ist. In den Zertifikatinformationen ist zudem angegeben, von welcher Stelle das Zertifikat typischerweise ausgestellt werden kann. Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden. Die Felder "Erweiterte Schlüsselverwendungen" und "Zuweisen zu" des Berichts sind äußerst nützlich und liefern Informationen zum Zweck und Speicherort der einzelnen Zertifikate.

![Zertifikat-Administratorbericht.](../../media/Certificates_Report_Admin_Report.png)

Überprüfen Sie die Verwendung und den Zweck jedes Zertifikats in der Bereitstellung sorgfältig, und achten Sie darauf, sie zu verstehen. Wenn eine Frage dazu vorliegt, was ein Zertifikat bewirkt, bestimmen Sie, mit welchem Server oder Dienst was geredet wird. Zertifikate in Skype for Business Server 2015 werden hauptsächlich für zwei Zwecke verwendet:

- Mutual Transport Layer Security (MTLS) – Die an der Kommunikation beteiligten Computer stellen jeweils ein Zertifikat vor, das ihre Identität gegenüber einem anderen Computer nachweist. Dies wird als Serverauthentifizierung bezeichnet. Die Kommunikation kann erst beginnen, wenn jeder Computer der Identität des anderen Computers vertraut.

- Verschlüsselung – Verschlüsselung (Secure Sockets Layer oder SSL und Transport Layer Security oder TLS) ist ein wichtiges Mittel, um die Kommunikation zu sichern, den Datenschutz zu gewährleisten und ein vertrauenswürdiges Kommunikations- und Zusammenarbeitssystem zu erstellen.

## <a name="review-the-firewall-report"></a>Überprüfen des Firewallberichts
<a name="Firewall_report"> </a>

Skype for Business Server 2015 verfügt über einen potenziell komplexen Satz von Firewallregeln. Das Planungstool reduziert diese Komplexität, indem es einen Bericht generiert, der alle Firewallanforderungen basierend auf den Eingabekriterien des Designers detailliert definiert. Der IT-Firewalladministrator kann die erforderlichen Regeln anhand dieses Berichts konfigurieren und definieren.

Aus Sicht der Firewallverwaltung sollte der Bericht sorgfältig überprüft werden, um sicherzustellen, dass es keine Konflikte mit den Firewall-Beendigungsregeln gibt und dass es keine Richtlinien oder Verfahren gibt, die verletzt werden könnten.

![Firewall-Administratorbericht.](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Überprüfen des DNS-Berichts
<a name="DNS_Report"> </a>

Der DNS-Bericht, der Teil des Administratorberichts ist, enthält alle empfohlenen und bekannten Einträge für das Domain Name System (DNS) in den internen, Umkreis- und externen Netzwerken. Wenn der Designer die Änderungen am Netzwerkdiagramm abgeschlossen hat und alle IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) auf ihre Produktionswerte definiert sind, stellt der DNS-Bericht eine hervorragende Konfigurationsressource bereit. Dieser Bericht kann auch als Dokument zur betriebsbereiten Problembehandlung dienen.

![DNS-Administratorbericht.](../../media/DNS_Report_Admin_Report.png)

Ihr DNS-Verwaltungsteam sollte den DNS-Bericht sorgfältig überprüfen lassen, um sicherzustellen, dass es keine Fehler gibt, die während der Bereitstellung Probleme verursachen oder eine Problembehandlungssitzung erschweren können.

## <a name="see-also"></a>Siehe auch
<a name="DNS_Report"> </a>

[Überprüfen der Administratorberichte](/previous-versions/office/lync-server-2013/lync-server-2013-reviewing-the-administrator-reports)
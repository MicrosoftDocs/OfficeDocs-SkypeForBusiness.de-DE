---
title: Überprüfen der Administratorberichte in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Die Administratorberichte stellen detaillierte Informationen zu Bereitstellung und Betrieb bereit. Die Berichte werden basierend auf der Auswahl generiert, die in Entwurfswebsites markiert ist. Der für den Entwurf verantwortlicher Benutzer kann die Administratorberichte durch Bearbeiten der Netzwerkdiagramme und Definieren der vollständigen IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für Server, Pools und Lastenausgleich ergänzen.
ms.openlocfilehash: b8c18dcfef28ac93e8c2036fee7f7b105f5c69bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823345"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Überprüfen der Administratorberichte in Skype for Business Server 2015

Die Administratorberichte stellen detaillierte Informationen zu Bereitstellung und Betrieb bereit. Die Berichte werden basierend auf der Auswahl generiert, die in **Entwurfswebsites markiert ist.** Der für den Entwurf verantwortlicher Benutzer kann die Administratorberichte durch Bearbeiten der Netzwerkdiagramme und Definieren der vollständigen IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für Server, Pools und Lastenausgleich ergänzen.

Mit dem Feature "Administratorberichte" können Sie:

- [Überprüfen des Zusammenfassungsberichts](review-the-administrator-reports.md#Summary_report)

- [Überprüfen des Zertifikatberichts](review-the-administrator-reports.md#Certificates_Report)

- [Überprüfen des Firewallberichts](review-the-administrator-reports.md#Firewall_report)

- [Überprüfen des DNS-Berichts](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Überprüfen des Zusammenfassungsberichts
<a name="Summary_report"> </a>

Der Skype for Business-Administratorbericht ist der erste von vier wertvollen Berichten, die Ihren Entwurf detailliert dokumentieren. Die Informationen in diesem Bericht und die anderen drei zugehörigen Berichte sind für Ihre Informationstechnologieteams nützlich:

![Allgemeiner Zusammenfassender Administratorbericht](../../media/General_Summary_Report_Admin_Report.png)

Der Zusammenfassungsbericht enthält allgemeine Konfigurationsinformationen zu Ihrem Edgenetzwerk. Der Standort, der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) und die IP-Adresse, der Netzwerktyp und kommentare, die für eine bestimmte Rolle spezifisch sind, werden dokumentiert.

Der Designer und jedes der Teams, die die Infrastruktur bereitstellen, verwalten und verwalten, sollten den Zusammenfassungsbericht auf Genauigkeit überprüfen und sicherstellen, dass Fehler mindestens auftreten.

Sie können auch ausführlichere Berichte anzeigen:

- Zertifikatbericht

- Firewallbericht

- DNS-Bericht

## <a name="review-the-certificates-report"></a>Überprüfen des Zertifikatberichts
<a name="Certificates_Report"> </a>

Der Zertifikatbericht enthält alle Zertifikate, die in der empfohlenen Skype for Business Server 2015-Bereitstellung erforderlich sind. Das Planungstool erstellt die eingegebenen Betreffnamen und alternativen Betreffnamen. Der unbearbeitende Standardtext kann eine potenzielle Herausforderung für das Team darstellen, das für das Anfordern und Ausstellen der Zertifikate zuständig ist. In den Zertifikatinformationen ist zudem angegeben, von welcher Stelle das Zertifikat typischerweise ausgestellt werden kann. Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden. Die Felder "Erweiterte Schlüsselverwendungen" und "Zuweisen zu" des Berichts sind äußerst nützlich und liefern Informationen zum Zweck und Speicherort der einzelnen Zertifikate.

![Bericht "Zertifikatadministrator"](../../media/Certificates_Report_Admin_Report.png)

Überprüfen Sie die Verwendung und den Zweck der einzelnen Zertifikate in der Bereitstellung sorgfältig, und achten Sie darauf, sie zu verstehen. Wenn sie fragen, was ein Zertifikat macht, bestimmen Sie, welcher Server oder Dienst mit welchem Server oder Dienst spricht. Zertifikate in Skype for Business Server 2015 werden zu zwei Hauptzwecken verwendet:

- MtLS (Mutual Transport Layer Security) – Die an der Kommunikation beteiligten Computer stellen jeweils ein Zertifikat vor, das ihre Identität für einen anderen Computer nachweist. Dies wird als Serverauthentifizierung bezeichnet. Die Kommunikation kann erst beginnen, wenn jeder Computer der Identität des anderen Computers vertraut.

- Verschlüsselung – Verschlüsselung (Secure Sockets Layer, SSL und Transport Layer Security oder TLS) ist eine wichtige Möglichkeit, um die Kommunikation zu sichern, den Datenschutz sicherzustellen und ein vertrauenswürdiges Kommunikations- und Zusammenarbeitssystem zu erstellen.

## <a name="review-the-firewall-report"></a>Überprüfen des Firewallberichts
<a name="Firewall_report"> </a>

Skype for Business Server 2015 verfügt über einen potenziell komplexen Satz von Firewallregeln. Das Planungstool reduziert diese Komplexität, indem ein Bericht generiert wird, der alle Firewallanforderungen basierend auf den Eingabekriterien des Designers detailliert definiert. Der IT-Firewalladministrator kann die erforderlichen Regeln anhand dieses Berichts konfigurieren und definieren.

Aus Sicht der Firewallverwaltung sollte der Bericht sorgfältig überprüft werden, um sicherzustellen, dass keine Konflikte mit dem Beenden von Firewallregeln auftreten und dass keine Richtlinien oder Verfahren verletzt werden.

![Bericht "Firewalladministrator"](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Überprüfen des DNS-Berichts
<a name="DNS_Report"> </a>

Im DNS-Bericht, der Teil des Administratorberichts ist, werden alle empfohlenen und bekannten Einträge für dns (Domain Name System) in internen, Umkreis- und externen Netzwerken angezeigt. Wenn der Designer die Änderungen am Netzwerkdiagramm abgeschlossen hat und alle IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für ihre Produktionswerte definiert sind, stellt der DNS-Bericht eine hervorragende Konfigurationsressource dar. Dieser Bericht kann auch als Dokument zur Problembehandlung dienen.

![BERICHT "DNS-Administrator"](../../media/DNS_Report_Admin_Report.png)

Lassen Sie ihr DNS-Verwaltungsteam den DNS-Bericht sorgfältig überprüfen, um sicherzustellen, dass keine Fehler vorhanden sind, die während der Bereitstellung Schwierigkeiten verursachen oder eine Problembehandlungssitzung erschweren können.

## <a name="see-also"></a>Siehe auch
<a name="DNS_Report"> </a>

[Überprüfen der Administratorberichte](https://technet.microsoft.com/library/1dee56a9-a033-4201-9765-e3469bd7d3e3.aspx)

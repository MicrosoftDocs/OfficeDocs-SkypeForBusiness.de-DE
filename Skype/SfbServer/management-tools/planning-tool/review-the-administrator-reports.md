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
description: Die Administratorberichte stellen detaillierte Informationen zu Bereitstellung und Betrieb bereit. Die Berichte werden basierend auf der Auswahl generiert, die unter Entwurfswebsites markiert ist. Der für den Entwurf verantwortlicher Benutzer kann die Administratorberichte durch Bearbeiten der Netzwerkdiagramme und Definieren der vollständigen IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für Server, Pools und Lastenausgleich ergänzen.
ms.openlocfilehash: dbef33351e7032e769e1d5ee68c5f0d582317eb6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104321"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Überprüfen der Administratorberichte in Skype for Business Server 2015

Die Administratorberichte stellen detaillierte Informationen zu Bereitstellung und Betrieb bereit. Die Berichte werden basierend auf der Auswahl generiert, die unter **Entwurfswebsites markiert ist.** Der für den Entwurf verantwortlicher Benutzer kann die Administratorberichte durch Bearbeiten der Netzwerkdiagramme und Definieren der vollständigen IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für Server, Pools und Lastenausgleich ergänzen.

Mit dem Administratorberichtsfeature können Sie:

- [Überprüfen des Zusammenfassenden Berichts](review-the-administrator-reports.md#Summary_report)

- [Überprüfen des Zertifikatberichts](review-the-administrator-reports.md#Certificates_Report)

- [Überprüfen des Firewallberichts](review-the-administrator-reports.md#Firewall_report)

- [Überprüfen des DNS-Berichts](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Überprüfen des Zusammenfassenden Berichts
<a name="Summary_report"> </a>

Der Skype for Business-Administratorbericht ist der erste von vier wertvollen Berichten, die Ihren Entwurf detailliert dokumentieren. Die Informationen in diesem Bericht und die drei anderen zugeordneten Berichte sind für Ihre Teams für Informationstechnologie nützlich:

![Allgemeiner Zusammenfassender Administratorbericht](../../media/General_Summary_Report_Admin_Report.png)

Der Zusammenfassungsbericht enthält allgemeine Konfigurationsinformationen zu Ihrem Edgenetzwerk. Der Standort, der vollqualifizierte Domänenname (FQDN) und die IP-Adresse, der Netzwerktyp und die Kommentare, die für eine bestimmte Rolle spezifisch sind, werden dokumentiert.

Der Designer und jedes der Teams, die die Infrastruktur bereitstellen, verwalten und warten, sollten den Zusammenfassenden Bericht auf Genauigkeit überprüfen und sicherstellen, dass Fehler mindestens auftreten.

Sie können auch ausführlichere Berichte anzeigen:

- Zertifikatbericht

- Firewallbericht

- DNS-Bericht

## <a name="review-the-certificates-report"></a>Überprüfen des Zertifikatberichts
<a name="Certificates_Report"> </a>

Der Zertifikatsbericht enthält alle Zertifikate, die in der empfohlenen Skype for Business Server 2015-Bereitstellung erforderlich sind. Das Planungstool erstellt Konten für die eingegebenen Betreffnamen und alternativen Betreffnamen. Standardtext, der nichtedited bleibt, kann eine potenzielle Herausforderung für das Team darstellen, das für das Anfordern und Ausstellen der Zertifikate zuständig ist. In den Zertifikatinformationen ist zudem angegeben, von welcher Stelle das Zertifikat typischerweise ausgestellt werden kann. Wenn die Infrastruktur nicht über eine interne Public Key-Infrastruktur (PKI) verfügt, können sämtliche Zertifikate über einen öffentlichen Zertifikatanbieter angefordert werden. Die Felder "Erweiterte Schlüsselverwendungen" und "Zuweisen zu" des Berichts sind äußerst nützlich und liefern Informationen zum Zweck und Speicherort der einzelnen Zertifikate.

![Bericht "Zertifikate-Administrator"](../../media/Certificates_Report_Admin_Report.png)

Überprüfen Sie die Verwendung und den Zweck der einzelnen Zertifikate in der Bereitstellung sorgfältig, und achten Sie darauf, sie zu verstehen. Wenn eine Frage zur Leistung eines Zertifikats besteht, bestimmen Sie, mit welchem Server oder Welchem Dienst gesprochen wird. Zertifikate in Skype for Business Server 2015 werden für zwei primäre Zwecke verwendet:

- Mutual Transport Layer Security (MTLS) – Die an der Kommunikation beteiligten Computer stellen jeweils ein Zertifikat vor, das ihre Identität für einen anderen Computer nachweist. Dies wird als Serverauthentifizierung bezeichnet. Die Kommunikation kann erst beginnen, wenn jeder Computer der Identität des anderen Computers vertraut.

- Verschlüsselung – Verschlüsselung (Secure Sockets Layer, SSL und Transport Layer Security oder TLS) ist eine wichtige Möglichkeit, um die Kommunikation zu sichern, den Datenschutz sicherzustellen und ein vertrauenswürdiges Kommunikations- und Zusammenarbeitssystem zu erstellen.

## <a name="review-the-firewall-report"></a>Überprüfen des Firewallberichts
<a name="Firewall_report"> </a>

Skype for Business Server 2015 verfügt über einen potenziell komplexen Satz von Firewallregeln. Das Planungstool reduziert diese Komplexität, indem ein Bericht generiert wird, der alle Firewallanforderungen basierend auf den Eingabekriterien des Designers detailliert definiert. Der IT-Firewalladministrator kann die erforderlichen Regeln anhand dieses Berichts konfigurieren und definieren.

Aus Sicht der Firewallverwaltung sollte der Bericht sorgfältig überprüft werden, um sicherzustellen, dass keine Konflikte mit dem Beenden von Firewallregeln auftreten und dass keine Richtlinien oder Verfahren verletzt werden können.

![Bericht "Firewalladministrator"](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Überprüfen des DNS-Berichts
<a name="DNS_Report"> </a>

Im DNS-Bericht, der Teil des Administratorberichts ist, werden alle empfohlenen und bekannten Einträge für das Domain Name System (DNS) in den internen, Umkreis- und externen Netzwerken details. Wenn der Designer die Bearbeitungen am Netzwerkdiagramm abgeschlossen hat und alle IP-Adressen und vollqualifizierten Domänennamen (Fully Qualified Domain Names, FQDNs) für ihre Produktionswerte definiert sind, stellt der DNS-Bericht eine hervorragende Konfigurationsressource dar. Dieser Bericht kann auch als Dokument zur Problembehandlung dienen.

![DNS-Administratorbericht](../../media/DNS_Report_Admin_Report.png)

Ihr DNS-Verwaltungsteam sollte den DNS-Bericht gründlich überprüfen, um sicherzustellen, dass keine Fehler vorhanden sind, die während der Bereitstellung zu Problemen führen oder eine Problembehandlungssitzung erschweren können.

## <a name="see-also"></a>Siehe auch
<a name="DNS_Report"> </a>

[Überprüfen der Administratorberichte](/previous-versions/office/lync-server-2013/lync-server-2013-reviewing-the-administrator-reports)
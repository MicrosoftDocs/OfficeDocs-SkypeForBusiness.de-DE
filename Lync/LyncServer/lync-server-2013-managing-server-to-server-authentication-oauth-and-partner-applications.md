---
title: Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen
TOCTitle: Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204817(v=OCS.15)
ms:contentKeyID: 49293691
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen

 

_**Letztes Änderungsdatum des Themas:** 2015-05-14_

Microsoft Lync Server 2013 muss in der Lage sein, mit anderen Anwendungen und Serverprodukten sicher und nahtlos zu kommunizieren. Sie können beispielsweise Lync Server 2013 so konfigurieren, dass Kontaktdaten und/oder Archivierungsdaten in Microsoft Exchange Server 2013 gespeichert werden. Dies ist aber nur möglich, wenn Lync Server und Exchange sicher miteinander kommunizieren können. Ebenso können Sie eine Lync Server-Konferenz von Microsoft SharePoint Server aus planen, aber auch dies ist wiederum nur möglich, wenn die beiden Server (SharePoint und Lync Server) sich gegenseitig vertrauen. Zwar ist es möglich, für die Lync-zu-Exchange-Kommunikation und für die Lync-zu-SharePoint-Kommunikation verschiedene Authentifizierungsmechanismen zu verwenden, aber besser und effizienter ist die Verwendung einer standardisierten Methode für die gesamte Server-zu-Server-Authentifizierung und -Autorisierung.

In Lync Server 2013 ist der Ansatz zur Verwendung einer standardisierten Methode für die gesamte Server-zu-Server-Authentifizierung implementiert. Für Version 2013 wird in Lync Server 2013 (sowie in anderen Microsoft Server-Produkten, einschließlich Exchange 2013 und Microsoft SharePoint Server) das OAuth-Protokoll (Open Authorization) für die gesamte Server-zu-Server-Authentifizierung und -Autorisierung unterstützt. Bei Verwendung von OAuth, einem von zahlreichen großen Websites verwendeten Standardauthentifizierungsprotokoll, werden Benutzeranmeldeinformationen und Kennwörter nicht von einem Computer an den anderen übergeben. Stattdessen basieren Authentifizierung und Autorisierung auf dem Austausch von Sicherheitstoken. Diese Token gewähren für einen bestimmten Zeitraum Zugriff auf bestimmte Gruppen von Ressourcen.

Die OAuth-Authentifizierung umfasst normalerweise drei Parteien: einen einzelnen Autorisierungsserver und die beiden Bereiche, die miteinander kommunizieren müssen. (Sie können auch eine Server-zu-Server-Authentifizierung durchführen, ohne einen Autorisierungsserver zu verwenden; dieser Prozess wird weiter unten in diesem Dokument erläutert.) Sicherheitstoken werden vom Autorisierungsserver (auch Sicherheitstokenserver genannt) für die beiden Bereiche ausgestellt, die miteinander kommunizieren müssen. Diese Token stellen sicher, dass die Kommunikation aus dem einen Bereich für den anderen Bereich als vertrauenswürdig gilt. Der Autorisierungsserver kann beispielsweise Token ausstellen, die sicherstellen, dass Benutzer aus einem bestimmten Lync Server 2013-Bereich auf einen angegebenen Exchange 2013-Bereich zugreifen können und umgekehrt.


> [!NOTE]
> Ein Bereich ist einfach ein Sicherheitscontainer. Standardmäßig wird von Lync Server 2013 Ihre SIP-Standarddomäne als OAuth-Bereich verwendet.



Lync Server 2013 unterstützt drei Server-zu-Server-Authentifizierungsszenarien. Mit Lync Server 2013 können Sie folgende Aufgaben durchführen:

  - Konfigurieren einer Server-zu-Server-Authentifizierung zwischen einer lokalen Installation von Lync Server 2013 und einer lokalen Installation von Exchange 2013 und/oder Microsoft SharePoint Server.

  - Konfigurieren einer Server-zu-Server-Authentifizierung zwischen einem Paar von Office 365-Komponenten (z. B. zwischen Microsoft Exchange und Microsoft Lync Server oder zwischen Microsoft Lync Server und Microsoft SharePoint).

  - Konfigurieren einer Server-zu-Server-Authentifizierung in einer standortübergreifenden Umgebung (d. h. Server-zu-Server-Authentifizierung zwischen einem lokalen Server und einer Office 365-Komponente).

Hinweis: Die Server-zu-Server-Authentifizierung wird derzeit nur von Exchange 2013, SharePoint Server und Lync Server 2013 unterstützt. Wenn Sie keinen dieser Server einsetzen, können Sie die OAuth-Authentifizierung nicht vollständig implementieren.

Beachten Sie, dass Sie die Server-zu-Server-Authentifizierung nicht verwenden müssen: Die Server-zu-Server-Authentifizierung ist nicht für die Bereitstellung von Lync Server 2013 erforderlich. Wenn Lync Server 2013 nicht mit anderen Servern (z. B. Exchange 2013) kommuniziert, dann ist die Server-zu-Server-Authentifizierung nicht erforderlich.

Die Server-zu-Server-Authentifizierung ist jedoch erforderlich, wenn Sie einige neue Lync Server-Features verwenden möchten, z. B. den "einheitlichen Kontaktspeicher". Wenn der einheitliche Kontaktspeicher verwendet wird, werden Lync Server 2013-Kontaktinformationen in Exchange 2013 anstatt in Lync Server gespeichert. Benutzer müssen so nur eine einzige Gruppe von Kontakten verwalten, auf die sie von Lync, Microsoft Outlook oder Microsoft Outlook Web Access aus schnell und einfach zugreifen können. Da für die Verwendung des einheitlichen Kontaktspeichers Lync Server 2013 Informationen für Exchange 2013 freigeben muss, müssen Sie eine Server-zu-Server-Authentifizierung verwenden, um das Feature bereitzustellen. Die Server-zu-Server-Authentifizierung ist zudem erforderlich, wenn Sie die Exchange-Archivierung verwenden, bei der die Aufzeichnungen von Chatsitzungen in Form von Exchange 2013-E-Mails und nicht als einzelne Datenbank-Datensätze gespeichert werden.

Damit die Office 365-Version von Lync Server mit ihrem Exchange-Gegenstück kommunizieren kann, muss Lync Server 2013 zuerst ein Sicherheitstoken vom Autorisierungsserver beziehen. Lync Server verwendet dann dieses Sicherheitstoken, um sich bei Exchange zu identifizieren. Die Office 365-Version von Exchange muss denselben Prozess durchlaufen, um mit Lync Server 2013 zu kommunizieren.

Für eine lokale Server-zu-Server-Authentifizierung zwischen zwei Microsoft-Servern muss kein Drittanbieter-Tokenserver verwendet werden. Serverprodukte wie Lync Server 2013 und Exchange 2013 haben einen integrierten Tokenserver, der für die Authentifizierung bei anderen Microsoft-Servern (z. B. SharePoint-Server) verwendet werden kann, die die Server-zu-Server-Authentifizierung unterstützen. So kann Lync Server 2013 beispielsweise selbst einen Sicherheitstoken ausstellen und signieren und dieses Token dann für die Kommunikation mit Exchange 2013 verwenden. In einem solchen Fall ist ein Drittanbieter-Tokenserver nicht erforderlich.

Zum Konfigurieren einer Server-zu-Server-Authentifizierung für eine lokale Implementierung von Lync Server 2013 sind zwei Schritte erforderlich:

  - Dem in Lync Server integrierten Tokenaussteller muss ein Zertifikat zugewiesen werden.

  - Der Server, mit dem Lync Server 2013 kommuniziert, muss eine "Partneranwendung sein". Wenn beispielsweise Lync Server 2013 mit Exchange 2013 kommunizieren muss, dann müssen Sie Exchange als Partneranwendung konfigurieren.


> [!NOTE]
> Bei einer "Partneranwendung" handelt es sich um eine beliebige Anwendung, mit der Lync Server 2013 direkt (also ohne Umweg über den Sicherheitstokenserver eines Drittanbieters) Sicherheitstoken austauschen kann.



Beachten Sie, dass OAuth eine Kernkomponente des Produkts ist und weder deaktiviert noch entfernt werden kann.

## Siehe auch

#### Konzepte

[Zuweisen eines Zertifikats für die Server-zu-Server-Authentifizierung zu Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Konfigurieren von Microsoft Lync Server 2013 in einer standortübergreifenden Umgebung](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)


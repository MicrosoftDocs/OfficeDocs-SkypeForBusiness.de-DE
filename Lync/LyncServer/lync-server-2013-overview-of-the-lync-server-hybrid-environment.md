---
title: 'Lync Server 2013: Übersicht über die Lync Server-Hybridumgebung'
TOCTitle: Übersicht über die Lync Server 2013-Hybridumgebung
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204669(v=OCS.15)
ms:contentKeyID: 49293162
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Lync Server 2013-Hybridumgebung

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013-Hybridumgebung bezeichnet eine Bereitstellung, bei der einige Benutzer auf dem lokalen Lync Server 2013 und andere in Lync Online gehostet sind. Für alle Benutzer gilt jedoch dieselbe Domäne, z. B. "user@contoso.com".

## Informationen zu diesem Handbuch

In diesem Handbuch sind die erforderlichen Aufgaben beschrieben, um Ihre Lync Server 2013-Umgebung für die Interoperabilität mit Lync Online zu konfigurieren und anschließend Benutzer aus Ihrer lokalen Bereitstellung nach Lync Online zu verschieben.

## Voraussetzungen

Folgende Anwendungen und Dienstprogramme müssen installiert sein, um die Aufgaben für die Konfiguration einer Hybridbereitstellung auszuführen. Die Installationsdateien für diese Programme sind auf den Installationsmedien für Ihre Bereitstellung sowie unter den Links in folgender Liste verfügbar:

  - [Active Directory-Verbunddienste (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Microsoft-Verzeichnissynchronisierungstool 9.1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Installieren von Windows PowerShell für das einmalige Anmelden mit AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Der Microsoft Online Services-Anmelde-Assistent (msoidcli-7.0.msi) ist im Office 365-Desktopsetup enthalten, das von der im Office 365-Adminportal verlinkten Downloads-Seite heruntergeladen werden kann.

## Administratoranmeldeinformationen

Wenn Sie aufgefordert werden, Ihre Administratoranmeldeinformationen abzugeben, verwenden Sie den Benutzernamen und das Kennwort für das Administratorkonto für Ihren Office 365-Mandanten. Diese Anmeldeinformationen verwenden Sie auch, wenn Sie Active Directory Federation Services (AD FS) 2.0, die Verzeichnissynchronisierung, das einmalige Anmelden, den Partnerverbund und das Verschieben von Benutzern zu Lync Online konfigurieren.

## Verbindung mit Lync Online PowerShell herstellen

Administratoren haben nun Möglichkeit, Windows PowerShell zum Verwalten von Lync Online und den Lync Online-Benutzerkonten zu verwenden. Hierzu müssen Sie zuerst das Lync Online-Connector-Modul aus dem Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688) herunterladen und installieren. Weitere Informationen zum Herunterladen, Installieren und Verwenden des Lync Online-Connector-Moduls sowie detaillierte Informationen zur Verwendung von Windows PowerShell für die Verwaltung von Lync Online finden Sie unter [Verwenden von Windows PowerShell zum Verwalten von Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).


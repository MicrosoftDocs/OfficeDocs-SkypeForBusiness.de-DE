---
title: Installieren Sie und öffnen Sie Verwaltung
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In diesem Thema wird beschrieben, wie zum Installieren und öffnen Sie die Bereitstellung und Verwaltung von Skype für Unternehmen benötigten Verwaltungstools.
ms.openlocfilehash: a27f16ab72d8fcdd4a5c440909dfb40baadd2572
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223164"
---
# <a name="install-and-open-administrative-tools"></a>Installieren Sie und öffnen Sie Verwaltung

In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie zum Bereitstellen und Verwalten von Skype für Business Server benötigen. Die Verwaltungstools werden standardmäßig auf jedem Server mit Skype für Business Server installiert. Darüber hinaus können Sie die Verwaltungstools auf anderen Computern, wie beispielsweise dedizierten Verwaltungskonsolen installieren. Es wird dringend empfohlen, dass Sie die Verwaltungstools installieren, auf einem Computer, die in der gleichen Domäne oder der Gesamtstruktur wie der Skype für Business Server-Bereitstellung, die Sie erstellen, um sicherzustellen, Vorbereitung von Active Directory Domain Services bereits Schritte abgeschlossen sind, die können Sie später verwenden Sie die Verwaltungstools auf diesem Computer um Ihrer Topologie zu veröffentlichen. Stellen Sie außerdem sicher, dass Sie die erforderlichen Anforderungen, ehe Sie installieren oder verwenden die Skype für Business Server-Verwaltungstools. Finden Sie unter in der Anforderungsdokumentation in [Skype für Business Server 2019](../../SfBServer2019/plan/system-requirements.md) oder [Skype für Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Wenn Ihre Organisation erfordert, dass Sie Internetinformationsdienste (Internet Information Services, IIS) und alle Webdienste auf einem anderen als dem Systemlaufwerk suchen, können Sie den Pfad zum Speicherort für die Skype für Dateien im Dialogfeld einrichten Business Server ändern. Bei der Installation der Setupdateien an diesem Pfad, einschließlich OCSCore.msi, wird die restlichen der Skype für Business Server-Dateien auf das Laufwerk ebenfalls bereitgestellt werden. 

## <a name="to-install-the-administrative-tools"></a>So installieren Sie die Verwaltungstools

1. Melden Sie sich als lokaler Administrator (Mindestanforderung) auf dem Computer, auf dem Sie die Verwaltungstools installieren möchten. Wenn Sie angemeldet sind als Standardbenutzer in Windows und (User Account Control, UAC) aktiviert ist, werden Sie für den lokalen Administrator oder eine entsprechende Domänen-und Benutzername und Kennwort aufgefordert werden.
2. Suchen Sie nach dem Installationsdatenträger auf Ihrem Computer, und doppelklicken Sie dann auf \Setup\amd64\Setup.exe.
3. Wenn Sie aufgefordert werden, installieren Sie das Microsoft Visual C++ befinden, klicken Sie auf **Ja**.
4. Klicken Sie auf der Seite Installationsspeicherort auf **OK**. Ändern Sie diesen Pfad zu einem anderen Speicherort oder Laufwerk, sollten Sie die Dateien an einen anderen Speicherort installiert haben.

    > [!Important]
    > Wenn Ihre Organisation erfordert, dass Sie Internetinformationsdienste (Internet Information Services, IIS) und alle Webdienste auf einem anderen als dem Systemlaufwerk suchen, können Sie den Pfad zum Speicherort für die Skype für Dateien im Dialogfeld einrichten Business Server ändern. Bei der Installation der Setupdateien an diesem Pfad, einschließlich OCSCore.msi, wird die übrige der Skype für Business Server-Dateien auf das Laufwerk zu bereitgestellt. 

5. Klicken Sie auf der Seite Endbenutzer-Lizenzvertrag lesen Sie die Lizenzbedingungen, klicken Sie auf **ich stimme**und klicken Sie dann auf **OK**. Dieser Schritt ist erforderlich, bevor Sie fortfahren können.
6. Klicken Sie auf der Seite Bereitstellungs-Assistent auf **Administratortools installieren**. 
7. Wenn die Installation erfolgreich abgeschlossen wird, klicken Sie auf **Beenden**.

Verwenden Sie die folgenden Verfahren können Sie Verwaltungstools bereitstellen, konfigurieren oder Problembehandlung Ihrer Skype für Business Server-Topologie öffnen.

- [Bereitstellungs-Assistent](#deployment-wizard)
- [Topologie-Generator](#topology-builder) 
- [Skype for Business Server-Systemsteuerung](#skype-for-business-server-control-panel)
- [Skype for Business Server-Verwaltungsshell](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Bereitstellungs-Assistent

Verwenden Sie das folgende Verfahren, um den Bereitstellungs-Assistenten lokal, um hinzufügen oder Entfernen von Komponentendateien starten.

**So starten Sie die Skype für Business Server-Bereitstellungs-Assistenten**

1. Melden Sie sich an dem Computer, auf dem die Skype für Business Server-Bereitstellungs-Assistenten als Mitglied der Gruppe Domänen-Admins und RTCUniversalServerAdmins installiert ist.
2. Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**und klicken Sie dann auf **Skype für Business Server-Bereitstellungs-Assistenten**.


## <a name="topology-builder"></a>Topologie-Generator 

Verwenden Sie das folgende Verfahren, um die Topologie-Generator, um die Server zu definieren, die Sie bereitstellen, in Ihrer Skype für Business Server-Topologie möchten öffnen.

**Öffnen Sie die Skype für Business Server-Topologie-Generator zum Entwerfen der Topologie**

1. Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    > [!NOTE]
    > Sie können eine Topologie mit einem Konto, das Mitglied der lokalen Benutzergruppe ist definieren, aber zum Lesen, veröffentlichen oder aktivieren eine Topologie mit der Installation von Skype für Business Server auf einem Server erforderlich ist, müssen Sie ein Konto, das Mitglied der Gruppe Domänen-Admins und ten ist verwenden e Gruppe RTCUniversalServerAdmins und, verfügt über Vollzugriff-Berechtigungen (d. h., lesen, schreiben und ändern) für die Dateifreigabe, die Sie beabsichtigen, verwenden Sie für den archivierungsdateispeicher vorhanden, damit der Topologie-Generator kann die erforderlichen discretionary Access Control Liste ( Zugriffssteuerungslisten), oder ein Konto mit gleichwertigen Berechtigungen.
 
2. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Topologie-Generator**.

## <a name="skype-for-business-server-control-panel"></a>Skype for Business Server-Systemsteuerung 

Verwenden Sie eines der folgenden Verfahren, um die Skype Business Server-Systemsteuerung zum Verwalten der Konfigurations von Servern, Benutzern, Clients und Geräte in Ihrer Umgebung zu öffnen.

> [!NOTE]
> Sie können ein Benutzerkonto, dem die Rolle "csadministrator", zum Ausführen von Aufgaben in der Skype für Business Server-Systemsteuerung zugewiesen ist. Andere Rollen können Sie die melden Sie sich an die Skype Business Server-Systemsteuerung bestimmte Verwaltungsaufgaben, hängt von den Vorgang ausführen, die Sie ausführen müssen. Beispielsweise können Sie die Rolle "csarchivingadministrator" zum Verwalten der Archivierung in der Skype Business Server-Systemsteuerung verwenden. Ausführliche Informationen zu Rollen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Ausführliche Informationen zu den Rollen, die Sie verwenden können, um eine bestimmte Aufgabe auszuführen, finden Sie in der Dokumentation für den Vorgang. 

**Öffnen Sie die Skype Business Server-Systemsteuerung aus einem beliebigen Computer innerhalb der Firewall Ihrer Organisation**

1. Ein Benutzerkonto, die die Rolle "csadministrator" oder Rollen, die entsprechenden Benutzerrechte und-Berechtigungen für den auszuführenden Vorgang hat zugewiesen ist, melden Sie sich an einem beliebigen Computer in Ihrer internen Bereitstellung mit einer minimale Auflösung von 1024 x 768.

    > [!IMPORTANT]
    > Wenn Sie einen Administration einfache uniform Resource Locator (URL) konfiguriert haben, können Sie die Skype Business Server-Systemsteuerung einem Internetbrowser zugreifen, die auf einem beliebigen Computer innerhalb der Firewall Ihrer Organisation ausgeführt wird. Ausführliche Informationen zum Konfigurieren der URL der einfachen finden Sie unter [Planung für einfache URLs](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) und [Bearbeiten oder konfigurieren einfacher URLs](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL für Ihre Organisation konfiguriert.

**Öffnen Sie die Skype Business Server-Systemsteuerung auf einem Computer mit Skype für Business Server**

1. Ein Benutzerkonto, das Mitglied der Rolle CsAdministrator oder Rollen, die entsprechenden Benutzerrechte und-Berechtigungen für den auszuführenden Vorgang hat ist, melden Sie sich an einem Computer, auf dem Sie Skype, für die Business Server oder zumindest installiert haben , der Skype für Business Server-Verwaltungstools. Zum Konfigurieren der Einstellungen, muss der Computer eine minimale Auflösung von 1024 x 768 verfügen.
2. Skype für Business Server-Systemsteuerung zu starten: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, zeigen Sie auf **Verwaltungstools**, zeigen Sie auf **Skype für Business Server**und klicken Sie dann auf **Skype Business Server-Systemsteuerung**.

## <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell 

Verwenden Sie das folgende Verfahren, um die Skype für Business Server-Verwaltungsshell zum Verwalten von Servern, Benutzern, Clients und Geräte in Ihrer Umgebung mithilfe der Befehlszeile zu öffnen.

> [!NOTE]
> Sie können ein Benutzerkonto, dem die Rolle "csadministrator", zum Ausführen von Aufgaben in der Skype für Business Server-Verwaltungsshell zugewiesen ist. Sie können melden Sie sich mit anderen Rollen bestimmte Verwaltungsaufgaben, je nach Aufgabe ausführen, die Sie ausführen müssen. Rolle "csarchivingadministrator" können Sie beispielsweise im Zusammenhang mit der Archivierung Verwaltung-Cmdlets ausführen. Ausführliche Informationen zu Rollen finden Sie unter [Planen der rollenbasierten Zugriffssteuerung](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Ausführliche Informationen zu den Rollen, die Sie verwenden können, um eine bestimmte-Cmdlet ausführen, finden Sie in der Dokumentation für das Cmdlet.<br/><br/>Sie können auch bestimmte Cmdlets mithilfe eines Benutzerkontos in den Gruppen RTCUniversalServerAdmins, RTCUniversalUserAdmins oder RTCUniversalReadOnlyAdmins, abhängig vom Cmdlet ausführen. 

**Öffnen von Skype für Business Server-Verwaltungsshell**

Wenn Sie ein Windows PowerShell-Fenster, statt die Skype für Business Server-Verwaltungsshell öffnen, kann nicht standardmäßig die Skype für Business Server-Cmdlets ausführen. Um die Skype für Business Server-Cmdlets von Windows PowerShell ausgeführt werden soll, geben Sie an der Windows PowerShell-Eingabeaufforderung Folgendes ein:

`Import-Module Lync`

Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.
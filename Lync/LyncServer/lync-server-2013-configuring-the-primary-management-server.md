---
title: Konfigurieren des primären Verwaltungsservers
TOCTitle: Konfigurieren des primären Verwaltungsservers
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204844(v=OCS.15)
ms:contentKeyID: 49293851
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des primären Verwaltungsservers

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Um die neuen Integritätsüberwachungsfähigkeiten in Microsoft Lync Server 2013 voll ausschöpfen zu können, müssen Administratoren zunächst einen Computer als primären Verwaltungsserver zuweisen. Anschließend müssen Sie auf diesem Computer System Center Operations Manager 2007 R2 oder System Center Operations Manager 2012 installieren. Außerdem müssen Sie eine unterstützte Version von SQL Server installieren, die als Ihre Operations Manager-Back-End-Datenbank fungiert. Wenn Sie System Center Operations Manager 2012 verwenden, können Sie eine der folgenden Versionen von SQL Server als Ihre Back-End-Datenbank verwenden:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Wenn Sie System Center Operations Manager 2007 R2 verwenden, wird empfohlen, entweder SQL Server 2005 Service Pack 4 oder SQL Server 2008 Service Pack 3 zu installieren. Sie können auch SQL Server 2008 R2 als Back-End-Datenbank für System Center Operations Manager 2007 R2 verwenden. Weitere Informationen zur Konfiguration von SQL Server 2008 R2 zur Verwendung mit System Center Operations Manager 2007 R2 finden Sie in Anhang 1 dieser Dokumentation.

Wenn Sie System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 installieren, müssen Sie alle Komponenten des Produkts installieren, einschließlich:

  - Betriebsdatenbank

  - Server

  - Konsole

  - Windows PowerShell-Cmdlets

  - Webkonsole

  - Berichterstellung

  - Data Warehouse

Diese Komponenten und ihre Installation werden in diesem Dokument nicht ausführlich beschrieben. Ausführliche Informationen zu System Center Operations Manager 2007 R2 finden Sie in der Dokumentation zu Operations Manager 2007 R2 unter [http://go.microsoft.com/fwlink/?linkid=257526\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=257526%26clcid=0x407) und der System Center Operations Manager 2012-Dokumentation unter [http://go.microsoft.com/fwlink/?linkid=257527\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=257527%26clcid=0x407). Wenn Sie SQL Server 2005 oder SQL Server 2008 Service Pack 1 als Ihre Back-End-Datenbank verwenden, sollten Sie diesen Anweisungen folgen.

Wenn Sie System Center Operations Manager 2012 verwenden, können Sie SQL Server 2012 als Ihre Back-End-Datenbank verwenden. Ausführliche Informationen zu SQL Server 2012 finden Sie in der Onlinedokumentation zu SQL Server 2012 unter [http://go.microsoft.com/fwlink/?linkid=257528\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=257528%26clcid=0x407).

Bedenken Sie, dass nur ein einziger primärer Verwaltungsserver pro Lync Server-Bereitstellung möglich ist. Außerdem können Sie zwar entweder System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 verwenden, jedoch nicht beide Anwendungen gleichzeitig ausführen – Sie müssen eine davon auswählen. Wenn Sie beispielsweise System Center Operations Manager 2012 ausführen, muss auch auf allen System Center-Agents System Center Operations Manager 2012 ausgeführt werden. Es ist nicht möglich, auf einigen Agents System Center Operations Manager 2012 und auf anderen System Center Operations Manager 2007 R2 auszuführen.


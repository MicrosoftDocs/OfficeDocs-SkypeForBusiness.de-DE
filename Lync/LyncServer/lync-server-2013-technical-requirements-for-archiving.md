---
title: 'Lync Server 2013: Technische Anforderungen für die Archivierung'
TOCTitle: Technische Anforderungen für die Archivierung
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205059(v=OCS.15)
ms:contentKeyID: 49294669
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für die Archivierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zu den technischen Anforderungen für Lync Server 2013 gehören die folgenden:

  - Infrastrukturanforderungen.

  - Für die Archivierung müssen alle erforderliche Softwarekomponenten installiert werden.

  - Speicheranforderungen für Daten zur Archivierung.

  - Skalierungsanforderungen und -überlegungen für die Archivierungsbereitstellung.

  - Leistungsanforderungen und -überlegungen für die Archivierungsdatenbanken.


> [!NOTE]
> Skalierungs- und Leistungsinformationen sind in dieser Lync Server 2013-Version nicht verfügbar.



## Infrastrukturanforderungen

Die Archivierungsinfrastrukturanforderungen für Lync Server 2013 sind mit denen für die Bereitstellung von Lync Server 2013 identisch. Ausführliche Informationen finden Sie unter [Ermitteln Ihrer Infrastrukturanforderungen für Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.

## Voraussetzungen für die Archivierung

Lync Server 2013 optimiert aus folgenden Gründen die Voraussetzungen für die Archivierung:

  - Der Archivierungsserver ist keine Serverrolle mehr. Stattdessen werden Datenerfassungs-Agenten auf den Front-End-Servern in einem Pool und Standard Edition-Server ausgeführt, um Daten für die Archivierung zu erfassen, sodass Sie keine separaten Systemplattformen zur Archivierung einrichten müssen.

  - Bei der Archivierung wird der Lync Server 2013-Dateispeicher für die Zwischenspeicherung von Dateien mit Besprechungsinhalten verwendet, sodass keine separate Dateispeicherung zur Archivierung eingerichtet werden muss.

  - In Lync Server 2013 ist Message Queuing nicht erforderlich.

## Speicheranforderungen für Daten zur Archivierung

Die Infrastruktur für Archivierungsspeicher muss zusätzlich eingerichtet werden. Dies umfasst eine oder beide der folgenden Infrastrukturen:

  - **Microsoft Exchange-Speicher**. Dateien mit Besprechungsinhalten, z. B. PowerPoint-Präsentationen, werden als Anlage archiviert. Wenn Sie die Microsoft Exchange-Integration verwenden möchten, damit die Archivdaten von Lync mit den Kompatibilitätsdaten von Exchange gespeichert werden, müssen Sie Exchange 2013 zur Bereitstellung von Exchange verwenden und sicherstellen, dass die maximale Speichergröße die Speicherung der Dateien mit Besprechungsinhalten unterstützt. Wenn Sie die Archivierung mithilfe der Integrationsoption von Microsoft Exchange bereitstellen, werden die Lync-Archivdaten mit den Kompatibilitätsdaten von Exchange 2013 nur für die Benutzer gespeichert, die auf Ihren Exchange 2013-Servern gehostet werden. Vor dem Bereitstellen und Aktivieren der Archivierung müssen Sie Exchange 2013 bereitstellen und die Archivierung mithilfe der Integrationsoption von Microsoft Exchange aktivieren. Wenn Sie sich für den Exchange 2013-Speicher entschieden haben, müssen Sie nur dann separate SQL Server-Datenbanken zur Archivierung bereitstellen, wenn Sie über Lync-Benutzer verfügen, die auf Ihren Exchange 2013-Servern gehostet werden.

  - **SQL Server-Datenbankspeicher zur Archivierung**. Damit Benutzer unterstützt werden, die nicht auf Ihren Exchange 2013-Servern gehostet werden oder wenn Sie die Integrationsoptionen von Microsoft Exchange nicht verwenden möchten, müssen Sie den Archivierungsspeicher mithilfe einer SQL Server-Datenbank bereitstellen. Lync Server 2013 unterstützt die folgenden 64-Bit-Versionen von SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    

    > [!NOTE]
    > Microsoft SQL Server 2008 R2 Express und Microsoft SQL Server 2012 Express werden nicht für die Archivierung unterstützt. 32-Bit-Versionen von SQL Server werden nicht unterstützt. Weitere Informationen zu SQL&nbsp;Server-Anforderungen und -Einschränkungen finden Sie unter <A href="lync-server-2013-database-software-support.md">Unterstützte Datenbanksoftware in Lync Server 2013</A> in der Planungsdokumentation oder in der Unterstützungsdokumentation.

    
    Sie müssen die SQL Server-Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren. Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank ( **LcsLog** ) beim Veröffentlichen der Topologie erstellen. Sie können die Datenbank auch später erstellen, z.\&nbsp;B. im Rahmen des Installationsverfahrens. Ausführliche Informationen zu SQL Server finden Sie im SQL\&nbsp;Server TechCenter unter [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x407).


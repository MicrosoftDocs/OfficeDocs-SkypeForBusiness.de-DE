---
title: 'Lync Server 2013: Einbinden des Sicherheitsdesks'
TOCTitle: Einbinden des Sicherheitsdesks
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398299(v=OCS.15)
ms:contentKeyID: 49293925
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einbinden des Sicherheitsdesks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

In Ihrem Unternehmen soll möglicherweise das Sicherheitsdesk in die Konfiguration für Notrufe eingebunden werden. Um entscheiden zu können, wie das Sicherheitsdesk in Ihre E9-1-1-Bereitstellung integriert werden kann, müssen Sie die folgenden Fragen beantworten.

  - **Soll das Sicherheitsdesk benachrichtigt werden, wenn ein Notruf abgesetzt wird?**  
    Sie können die Ortungsrichtlinie so konfigurieren, dass Lync Server Benachrichtigungen per Sofortnachricht an die Lync SIP-Adressen eines oder mehrerer Sicherheitsmitarbeiter sendet. Diese Benachrichtigungen enthalten den Namen, die Nummer und den Standort der Person, die den Notruf abgesetzt hat. Dadurch wird der Umgang mit dem Notfall für das Sicherheitspersonal erleichtert.

<!-- end list -->

  - **Möchten Sie für Notrufe eine Konferenzschaltung mit dem Sicherheitsdesk einrichten?**  
    Sofern vom Anbieter für die Notrufunterstützung unterstützt, können Sie in der Ortungsrichtlinie eine Rückrufnummer für Notrufe einschließen. Diese Nummer wird vom Anbieter verwendet, um für Notrufe eine Konferenzschaltung mit dem Sicherheitspersonal einzurichten.


> [!NOTE]
> Falls erforderlich, können Sie für jede Ortungsrichtlinie unterschiedliches Notrufpersonal konfigurieren. Auf diese Weise können Sie die Maßnahmen für unterschiedliche Unternehmensbereiche anpassen oder ein unterschiedliches Verhalten für Notrufe konfigurieren, die von innerhalb oder von außerhalb des Netzwerks erfolgen. Geben Sie die Mitarbeiter, die benachrichtigt werden sollen, mithilfe von Verteilergruppen an.



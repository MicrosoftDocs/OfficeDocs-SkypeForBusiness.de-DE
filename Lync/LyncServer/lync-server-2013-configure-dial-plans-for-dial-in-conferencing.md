---
title: 'Lync Server 2013: Konfigurieren von Wählplänen für Einwahlkonferenzen'
TOCTitle: Konfigurieren von Wählplänen für Einwahlkonferenzen
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412768(v=OCS.15)
ms:contentKeyID: 49294967
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern. Stellen Sie sicher, dass in jedem Satz mit Wähleinstellungen mindestens eine Normalisierungsregel die Telefondurchwahlen in vollständige Rufnummern im E.164-Format konvertiert. Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben. Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.

Gehen Sie folgendermaßen vor, um Wähleinstellungen für Einwahlkonferenzen einzurichten:

  - Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen oder nicht, fügen Sie zu den Wähleinstellungen eine Region für Einwahlkonferenzen hinzu und stellen Sie sicher, dass Ihre Einwahlnummern einwandfrei von einer Normalisierungsregel umgewandelt werden. Eine genaue Anleitung finden Sie unter [Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Wenn Sie Enterprise-VoIP nicht bereitstellen, erstellen Sie Wählpläne für Ihre Einwahlnummern. Fügen Sie auf jeden Fall eine Region für Einwahlkonferenzen hinzu. Genaue Informationen finden Sie unter [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Wenn Sie Enterprise-VoIP bereitgestellt haben, Enterprise-VoIP ändern Sie die Wählpläne ggf. ab. Fügen Sie Regionen hinzu und verwenden Sie geeignete Normalisierungsregeln für Einwahlnummern. Eine genaue Anleitung finden Sie unter [Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Darüber hinaus können Sie auch Einwahlpläne erstellen, die nur für Einwahlnummern gelten. Eine genaue Anleitung hierzu finden Sie unter [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Ausführliche Informationen zum Planen von Regionen finden Sie unter [Anforderungen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in der Planungsdokumentation.

## In diesem Abschnitt

  - [Anzeigen von Informationen zu Wählplänen in Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definieren von Normalisierungsregeln in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)


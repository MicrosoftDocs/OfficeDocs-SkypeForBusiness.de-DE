---
title: 'Lync Server 2013: Bearbeiten des Entwurfs'
TOCTitle: Bearbeiten des Entwurfs
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558608(v=OCS.15)
ms:contentKeyID: 52056282
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bearbeiten des Entwurfs in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Nach Beantwortung der anfänglichen Fragen können Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und die IP-Adressen der Website bearbeiten. Doppelklicken Sie hierzu auf der Seite **Globale Topologie** auf den Standort, den Sie bearbeiten möchten.

Das Planungstool zeigt die Topologie für den ausgewählten Standort an. Im unteren Bereich der Seite für den Standort werden vier Registerkarten angezeigt:

![Planungstool – Standorttopologie](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planungstool – Standorttopologie")

  - Standorttopologie - Die aktuell angezeigte Seite mit einer optischen Übersicht der empfohlenen Topologie.

  - Edgenetzwerkdiagramm - Auf der Seite mit dem Edgenetzwerkdiagramm führt der für den Entwurf verantwortliche Benutzer die meisten Aufgaben im Planungstool aus. Das Diagramm zeigt die Netzwerkkonfiguration für eine empfohlene Lync Server 2013-Topologie. Hierzu zählen die bearbeitbaren Einträge für IP-Adressen und FQDNs für Server, Pool und Lastenausgleichsmodule sowohl für Hardware als auch DNS (Domain Name System).

  - Edgeverwaltungsbericht - Der Edgeverwaltungsbericht umfasst insgesamt vier Berichte:
    
    ![Edgeverwaltungsbericht (Seite)](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edgeverwaltungsbericht (Seite)")  
    
      - Zusammenfassungsbericht - Ein allgemeiner Bericht zu den Einstellungen der Edgenetzwerkkonfiguration. Wenn Sie auf der Seite **Edge-Netzwerkdiagramm** die TCP-IP- und FQDN-Werte der Topologie in die der tatsächlichen Bereitstellung ändern, werden diese Adressen und Namen hier dargestellt. Andernfalls wird hier der Standardtext angezeigt.
    
      - Zertifikatbericht - Der Zertifikatbericht führt den Antragstellernamen und alternative Antragstellernamen für die Zertifikate auf, die für die Topologie benötigt werden.
    
      - Firewallbericht - Im Firewallbericht werden Informationen aufgeführt, die zum Konfigurieren von Umkreisfirewalls in der Infrastruktur benötigt werden. Diese umfassen die IP-Adressen (entweder die Standardwerte oder die bearbeiteten Werte), Serverrolle, Quell-IP und Port, Ziel-IP und Port, Transportprotokoll, Anwendungsprotokoll und relevante Hinweise.
    
      - DNS-Bericht - Im DNS-Bericht werden Informationen zu den DNS-Einträgen aufgeführt, die Sie erstellen müssen. Hierzu zählen Eintragstyp, FQDN, IP-Adresse und Hinweise zum ordnungsgemäßen Betrieb.

  - Standortzusammenfassung - Die Standortzusammenfassung liefert einen Überblick über die Auswahl, die entweder bei den anfänglichen Fragen oder durch Angeben der Werte in **Websites entwerfen** getroffen wurde. Es werden auch Kapazitätsinformationen angezeigt.
    

    > [!NOTE]
    > Die Informationen auf der Seite mit der Standortzusammenfassung sind auf den jeweiligen Entwurf zugeschnitten und enthält möglicherweise nicht alle Abschnitte oder Informationen, die hier besprochen werden.



## Siehe auch

#### Konzepte

[Bearbeiten des Netzwerkkonfigurationsdiagramms](lync-server-2013-editing-the-network-configuration-diagram.md)


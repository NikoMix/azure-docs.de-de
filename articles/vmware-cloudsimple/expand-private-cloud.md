---
title: Erweitern einer privaten Cloud in Azure VMware Solution by CloudSimple
description: Beschreibt, wie Sie eine vorhandene private CloudSimple-Cloud erweitern, um die Kapazität eines vorhandenen oder neuen Clusters zu erweitern.
author: Ajayan1008
ms.author: v-hborys
ms.date: 06/06/2019
ms.topic: article
ms.service: azure-vmware-cloudsimple
ms.reviewer: cynthn
manager: dikamath
ms.openlocfilehash: c469ea3f104e71eb80010d4a5cd421eab6184fcf
ms.sourcegitcommit: d7d5f0da1dda786bda0260cf43bd4716e5bda08b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "97895855"
---
# <a name="expand-a-cloudsimple-private-cloud"></a>Erweitern einer privaten CloudSimple-Cloud

CloudSimple bietet die Flexibilität, eine private Cloud dynamisch zu erweitern. Sie können mit einer kleineren Konfiguration beginnen und diese dann mit wachsenden Kapazitätsanforderungen erweitern. Alternativ können Sie eine private Cloud basierend auf dem aktuellen Bedarf erstellen und dann mit zunehmender Nutzung erweitern.

Eine private Cloud besteht aus einem oder mehreren vSphere-Clustern. Jeder Cluster kann 3 bis 16 Knoten enthalten.  Wenn Sie eine private Cloud erweitern, fügen Sie einem vorhandenen Cluster Knoten hinzu oder erstellen einen neuen Cluster. Um einen vorhandenen Cluster zu erweitern, müssen die zusätzlichen Knoten denselben Typ (SKU) wie die vorhandenen Knoten aufweisen. Beim Erstellen eines neuen Clusters können die Knoten einen unterschiedlichen Typ haben. Weitere Informationen zu Grenzwerten für private Clouds finden Sie im Artikel [Übersicht über private CloudSimple-Clouds](cloudsimple-private-cloud.md).

Eine private Cloud wird mit einem **Standard-Datencenter** in vCenter erstellt.  Jedes Datencenter dient als Verwaltungsentität auf oberster Ebene.  Bei einem neuen Cluster bietet CloudSimple die Möglichkeit, den Cluster einem vorhandenen Datencenter hinzuzufügen oder ein neues Datencenter zu erstellen.

Bei einer neuen Clusterkonfiguration wird die VMware-Infrastruktur durch CloudSimple konfiguriert.  Die Einstellungen umfassen Speichereinstellungen für vSAN-Datenträgergruppen, VMware High Availability (HA) und Distributed Resource Scheduler (DRS).

Eine private Cloud kann mehrfach erweitert werden. Die Erweiterung ist jedoch nur bis zur maximal zulässigen Knotenanzahl möglich. Jedes Mal, wenn Sie eine private Cloud erweitern, fügen Sie einem vorhandenen Cluster Knoten hinzu oder erstellen einen neuen Cluster.

## <a name="before-you-begin"></a>Voraussetzungen

Bevor Sie eine private Cloud erweitern können, müssen Knoten bereitgestellt werden.  Weitere Informationen zum Bereitstellen von Knoten finden Sie im Artikel [Kaufen von Knoten für VMware Solution by CloudSimple – Azure](create-nodes.md).  Zum Erstellen eines neuen Clusters benötigen Sie mindestens drei verfügbare Knoten derselben SKU.

## <a name="sign-in-to-azure"></a>Anmelden bei Azure

Melden Sie sich unter [https://portal.azure.com](https://portal.azure.com) beim Azure-Portal an.

## <a name="expand-a-private-cloud"></a>Erweitern einer privaten Cloud

1. [Rufen Sie das CloudSimple-Portal auf](access-cloudsimple-portal.md).

2. Öffnen Sie die Seite **Resources** (Ressourcen), und wählen Sie die private Cloud aus, die Sie erweitern möchten.

3. Klicken Sie im Abschnitt „Summary“ (Zusammenfassung) auf **Expand** (Erweitern).

    ![Erweitern einer privaten Cloud](media/resources-expand-private-cloud.png)

4. Wählen Sie aus, ob Sie Ihren vorhandenen Cluster erweitern oder einen neuen vSphere-Cluster erstellen möchten. Während Sie Änderungen vornehmen, wird die Zusammenfassung auf der Seite aktualisiert.

    * Um Ihren vorhandenen Cluster zu erweitern, klicken Sie auf **Expand existing cluster** (Vorhandenen Cluster erweitern). Wählen Sie den zu erweiternden Cluster aus, und geben Sie die Anzahl der Knoten ein, die Sie hinzufügen möchten. Jeder Cluster kann maximal 16 Knoten enthalten.
    * Klicken Sie zum Hinzufügen eines neuen Clusters auf **Create new cluster** (Neuen Cluster erstellen). Geben Sie einen Namen für den Cluster ein. Wählen Sie ein vorhandenes Datencenter aus, oder geben Sie einen Namen ein, um ein neues Datencenter zu erstellen. Wählen Sie den Knotentyp aus. Sie können einen anderer Knotentyp auswählen, wenn Sie einen neuen vSphere-Cluster erstellen, aber nicht, wenn Sie einen vorhandenen vSphere-Cluster erweitern. Wählen Sie die Anzahl der Knoten aus. Jeder neue Cluster muss mindestens über drei Knoten verfügen.

    ![Erweitern einer privaten Cloud – Knoten hinzufügen](media/resources-expand-private-cloud-add-nodes.png)

5. Klicken Sie auf **Submit** (Senden), um die private Cloud zu erweitern.

## <a name="next-steps"></a>Nächste Schritte

* [Nutzen von virtuellen VMware-Computern in Azure](quickstart-create-vmware-virtual-machine.md)
* Weitere Informationen zu [privaten Clouds](cloudsimple-private-cloud.md)
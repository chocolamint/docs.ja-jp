---
title: Azure コンテナー サービス (つまり、Kubernetes) に Windows コンテナーを展開するタイミング
description: Azure のクラウドと Windows コンテナーでの既存の .NET アプリケーションを最新化 |Azure コンテナー サービス (つまり、Kubernetes) に Windows コンテナーを展開するタイミング
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="1ee6f-103">Azure コンテナー サービス (つまり、Kubernetes) に Windows コンテナーを展開するタイミング</span><span class="sxs-lookup"><span data-stu-id="1ee6f-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="1ee6f-104">Azure のコンテナー サービスは、Azure の特に人気のオープン ソース ツールとテクノロジの構成を最適化します。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="1ee6f-105">移植性、コンテナーと、アプリケーションの構成の両方を提供する、開いているソリューションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="1ee6f-106">サイズ、ホストの数と、orchestrator ツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="1ee6f-107">Azure のコンテナー サービスは、のインフラストラクチャを処理します。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="1ee6f-108">既にしているオープン ソース orchestrators Kubernetes、Docker Swarm、DC/OS など場合、は、コンテナー ワークロードをクラウドに移動する、既存の管理方法を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="1ee6f-109">慣れているアプリケーションの管理ツールを使用し、任意の orchestrator の標準 API エンドポイントを介して接続します。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="1ee6f-110">これらすべての orchestrators は、Linux Docker コンテナーを使用しているが、Windows コンテナーのプレビュー状態である可能性がありますのみとお考えの場合、完成度の高い環境です。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="1ee6f-111">たとえば、Kubernetes でのサポートのコンテナーはネイティブ (ファーストクラス市民) Kubernetes で Windows コンテナーを使用しても (初期 2018 時点で ACS でのプレビュー) で効果的です。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="1ee6f-112">重要な注意事項: 展開し、"複数 PaaS"バージョンの Kubernetes 用 ACS (Azure コンテナー サービス) AKS (Azure Kubernetes サービス)、ただし、Windows コンテナーはまだサポートされていません Q2 2018 時点では近日サポートされます。</span><span class="sxs-lookup"><span data-stu-id="1ee6f-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1ee6f-113">[前へ](when-to-deploy-windows-containers-to-service-fabric.md)
[次へ](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="1ee6f-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
# 简易开发使用说明


## 开发环境准备

### 设置代理访问 github

git config --global http.proxy socks5://127.0.0.1:8880
git config --global https.proxy socks5://127.0.0.1:8880



### 修改 NPM 镜像源

设置镜像源
npm config set registry https://registry.npmmirror.com/

设置官方镜像源
npm config set registry https://registry.npmjs.org/

查看npm仓库中的最新版本
npm view <package_name> version 

## npm 安装
npm install -g @qwen-code/qwen-code@latest
qwen --version

查询安装的模块
npm list -g

卸载模块
npm uninstall -g @qwen-code/qwen-code@latest
npm uninstall -g @qwen-code/qwen-code


## 源码安装

git clone https://github.com/peaklau2008/qwen-code.git
cd qwen-code

npm install
npm install -g .

卸载
npm uninstall -g .

提交代码

Generate a SSH key pair (private/public)
chmod 644 ~/.ssh/id_rsa.pub
chmod 600 ~/.ssh/id_rsa

Copy the public SSH key to GitHub
Test the SSH key:
ssh -T git@github.com

git remote set-url origin git@github.com:peaklau2008/qwen-code.git
git push

## 工具使用

1. web_fetch

 web_fetch(url="https://baike.baidu.com/item/%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD/9180", prompt="Can you summarize the main points of this article?")

2，web_search

web_search(query="rdma")

tavily

"body": "{\"api_key\":\"sk\",\"query\":\"rdma\",\"search_depth\":\"advanced\",\"max_results\":5,\"include_answer\":true}"

{
  "query": "rdma",
  "follow_up_questions": null,
  "answer": null,
  "images": [],
  "results": [
    {
      "url": "https://en.wikipedia.org/wiki/Remote_direct_memory_access",
      "title": "Remote direct memory access - Wikipedia",
      "content": "In computing, **remote direct memory access** (**RDMA**) is a direct memory access from the memory of one computer into that of another without involving either one's operating system. RDMA supports zero-copy networking by enabling the network adapter to transfer data from the wire directly to application memory or from application memory directly to the wire, eliminating the need to copy data between application memory and the data buffers in the operating system. Software vendors, such as IBM, Red Hat and Oracle Corporation, support these APIs in their latest products, and as of 2013 engineers have started developing network adapters that implement RDMA over Ethernet. 6. **^** \"40Gbe SMB Direct RDMA Over Ethernet For Windows Server 2012 - Chelsio Communications\". \"40Gbe SMB Direct RDMA Over Ethernet For Windows Server 2012 - Chelsio Communications\".",
      "score": 0.9287263,
      "raw_content": null
    },
    {
      "url": "https://www.starwindsoftware.com/blog/rdma-a-deep-dive-into-remote-direct-memory-access/",
      "title": "RDMA: A Deep Dive into Remote Direct Memory Access - StarWind",
      "content": "RDMA is a technology that enables direct data transfers between the memory of two devices, bypassing the CPU, cache, and operating system.",
      "score": 0.92074,
      "raw_content": null
    },
    {
      "url": "https://docs.nvidia.com/networking/display/MLNXOFEDv543750LTS/RDMA+over+Converged+Ethernet+(RoCE)",
      "title": "RDMA over Converged Ethernet (RoCE) - NVIDIA Docs",
      "content": "Remote Direct Memory Access (RDMA) is the remote memory management capability that allows server-to-server data movement directly between",
      "score": 0.90692574,
      "raw_content": null
    },
    {
      "url": "https://www.techtarget.com/searchstorage/definition/Remote-Direct-Memory-Access",
      "title": "Remote Direct Memory Access (RDMA) - TechTarget",
      "content": "Like locally based Direct Memory Access (DMA), RDMA improves throughput and performance because it frees up resources, resulting in faster data transfer rates and lower latency between RDMA-enabled systems. RDMA facilitates more direct and efficient data movement into and out of a server by implementing a transport protocol in the network interface card (NIC) located on each communicating device. When that data is shared over a network, RDMA can help increase data-access performance, especially when used in conjunction with NVM Express over Fabrics (NVMe-oF). NVMe-oF with RDMA makes it possible for organizations to take fuller advantage of their NVMe storage devices when connecting over Ethernet or InfiniBand networks, resulting in faster performance and lower latency.",
      "score": 0.8947989,
      "raw_content": null
    },
    {
      "url": "https://www.digitalocean.com/community/conceptual-articles/rdma-high-performance-networking",
      "title": "RDMA Explained: The Backbone of High-Performance Computing",
      "content": "RDMA allows direct data transfers between two computers' memories without involving the CPU, operating system, or most network stack components.",
      "score": 0.8682137,
      "raw_content": null
    }
  ],
  "response_time": 0.87,
  "request_id": "2173a137-cba3-468f-9510-911a6c4ae7a0"
}




## 问题解决

1. 遇到npm install 安装依赖报错时

npm cache clean --force
rm -Rf node_modules
rm -Rf packages/cli/node_modules
rm -Rf packages/core/node_modules
rm -Rf package-lock.json

2. 遇到Identifier 'createRequire' has already been declared

注释掉node_modules/fdir/dist/index.mjs中一行
//import { createRequire } from "module";

3. silly placeDep ROOT @testing-library/react@16.3.0 KEEP for: @qwen-code/qwen-code@0.0.12 want: ^16.3.0
检查冲突
npm ls @testing-library/react



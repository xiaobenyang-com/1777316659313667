# 基金知识查询服务器 

一个基于Model Context Protocol (MCP)的基金知识库服务器，提供基金相关知识的查询和检索功能，支持多种部署模式和协议。
A fund knowledge base server based on Model Context Protocol (MCP), providing query and retrieval functions of fund-related knowledge, and supporting multiple deployment modes and protocols.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| fund.echo | Echo back a message. Example interface for scaffold. |
| fund.knoewledge | 获取的知识库列表信息 |
| fund.stock_search | 搜索股票信息，基于东方财富API |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659313667](https://mcp.xiaobenyang.com/inspector/1777316659313667)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659313667](https://mcp.xiaobenyang.com/inspector/1777316659313667)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "基金知识查询服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659313667/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "基金知识查询服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659313667/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "基金知识查询服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659313667",
          },
          "transport": "stdio"
        }
      }
}

```

# 讨论 API

## 列出讨论

<table>
  <tr>
    <th align="right">请求</th>
    <td><code>GET /api/discuss/lists</code></td>
  </tr>
  <tr>
    <th align="right">参数</th>
    <td><code>application/x-www-form-urlencoded</code> (<code>{ forum?: string; page?: number; }</code>)</td>
  </tr>
  <tr>
    <th align="right">响应主体</th>
    <td><code>application/json</code> (<code>{ status: number; data: LList&lt;LPost&gt;; }</code>)</td>
  </tr>
</table>

## 列出发起的讨论

<table>
  <tr>
    <th align="right">请求</th>
    <td><code>GET /fe/api/user/createdPosts</code></td>
  </tr>
  <tr>
    <th align="right">参数</th>
    <td><code>application/x-www-form-urlencoded</code> (<code>{ page?: number; orderBy?: string; }</code>)</td>
  </tr>
  <tr>
    <th align="right">响应主体</th>
    <td><code>application/json</code> (<code>{ posts: List&lt;Post&gt;; }</code>)</td>
  </tr>
</table>

## 获取讨论

<table>
  <tr>
    <th align="right">请求</th>
    <td><code>GET /api/discuss/detail/:id</code></td>
  </tr>
  <tr>
    <th align="right">响应主体</th>
    <td><code>application/json</code> (<code>{ status: number; data: LPostDetails; }</code>)</td>
  </tr>
</table>

## 获取回复

<table>
  <tr>
    <th align="right">请求</th>
    <td><code>GET /api/discuss/replies/:id</code></td>
  </tr>
  <tr>
    <th align="right">响应主体</th>
    <td><code>application/json</code> (<code>{ status: number; data: LList&lt;LReply&gt;; }</code>)</td>
  </tr>
</table>

## 发表回复

<table>
  <tr>
    <th align="right">请求</th>
    <td><code>POST /api/discuss/reply/:id</code></td>
  </tr>
  <tr>
    <th align="right">请求主体</th>
    <td><code>application/x-www-form-urlencoded</code> (<code>{ content: string; verify?: string; }</code>)</td>
  </tr>
  <tr>
    <th align="right">响应主体</th>
    <td><code>application/json</code> (<code>{ status: number; data: []; }</code>)</td>
  </tr>
</table>

## 删除回复

**注**: 需要 [`X-CSRF-Token`](misc.md#获取-csrf-token).

<table>
  <tr>
    <th align="right">请求</th>
    <td><code>DELETE /api/discuss/deleteReply/:id</code></td>
  </tr>
  <tr>
    <th align="right">响应主体</th>
    <td><code>application/json</code> (<code>{ status: number; data: []; }</code>)</td>
  </tr>
</table>

## 举报讨论

<table>
  <tr>
    <th align="right">请求</th>
    <td><code>POST /api/report/post</code></td>
  </tr>
  <tr>
    <th align="right">请求主体</th>
    <td><code>application/x-www-form-urlencoded</code> (<code>{ relevantID: number; reason: string; }</code>)</td>
  </tr>
  <tr>
    <th align="right">响应主体</th>
    <td><code>application/json</code> (<code>{ status: number; data: string; }</code>)</td>
  </tr>
</table>

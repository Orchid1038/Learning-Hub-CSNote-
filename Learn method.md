<div class="markdown prose w-full break-words dark:prose-invert dark"><h1>C# Array Algorithm Notes</h1><h2>1. Introduction</h2><p>在C#中，陣列是基本的資料結構，它允許你儲存和操作元素的集合。理解與陣列相關的各種演算法對於高效的程式設計至關重要。</p><h2>2. Basic Array Operations</h2><h3>2.1 Creating an Array</h3><p>在C#中，創建陣列使用以下語法：</p><pre><div class="bg-black rounded-md"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-csharp"><span class="hljs-built_in">int</span>[] myArray = <span class="hljs-keyword">new</span> <span class="hljs-built_in">int</span>[<span class="hljs-number">5</span>];
</code></div></div></pre><p>這創建了一個包含5個元素的整數陣列。</p><h3>2.2 Accessing Array Elements</h3><p>使用零起始的索引來訪問陣列中的元素：</p><pre><div class="bg-black rounded-md"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-csharp"><span class="hljs-built_in">int</span> <span class="hljs-keyword">value</span> = myArray[<span class="hljs-number">2</span>]; <span class="hljs-comment">// 訪問第三個元素</span>
</code></div></div></pre><h3>2.3 Modifying Array Elements</h3><p>你可以以相同的方式修改陣列元素：</p><pre><div class="bg-black rounded-md"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-csharp">myArray[<span class="hljs-number">1</span>] = <span class="hljs-number">10</span>; <span class="hljs-comment">// 修改第二個元素</span>
</code></div></div></pre><h2>3. Common Array Algorithms</h2><h3>3.1 Linear Search</h3><p>一個簡單的演算法，用於查找目標值的位置：</p><pre><div class="bg-black rounded-md"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-csharp"><span class="hljs-function"><span class="hljs-built_in">int</span> <span class="hljs-title">LinearSearch</span>(<span class="hljs-params"><span class="hljs-built_in">int</span>[] array, <span class="hljs-built_in">int</span> target</span>)</span>
{
    <span class="hljs-keyword">for</span> (<span class="hljs-built_in">int</span> i = <span class="hljs-number">0</span>; i &lt; array.Length; i++)
    {
        <span class="hljs-keyword">if</span> (array[i] == target)
            <span class="hljs-keyword">return</span> i;
    }
    <span class="hljs-keyword">return</span> <span class="hljs-number">-1</span>; <span class="hljs-comment">// 目標未找到</span>
}
</code></div></div></pre><h3>3.2 Binary Search</h3><p>對於排序過的陣列，二分搜尋更有效：</p><pre><div class="bg-black rounded-md"><div class="flex items-center relative text-gray-200 bg-gray-800 gizmo:dark:bg-token-surface-primary px-4 py-2 text-xs font-sans justify-between rounded-t-md"></div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-csharp"><span class="hljs-function"><span class="hljs-built_in">int</span> <span class="hljs-title">BinarySearch</span>(<span class="hljs-params"><span class="hljs-built_in">int</span>[] array, <span class="hljs-built_in">int</span> target</span>)</span>
{
    <span class="hljs-built_in">int</span> left = <span class="hljs-number">0</span>, right = array.Length - <span class="hljs-number">1</span>;

    <span class="hljs-keyword">while</span> (left &lt;= right)
    {
        <span class="hljs-built_in">int</span> mid = left + (right - left) / <span class="hljs-number">2</span>;

        <span class="hljs-keyword">if</span> (array[mid] == target)
            <span class="hljs-keyword">return</span> mid;

        <span class="hljs-keyword">if</span> (array[mid] &lt; target)
            left = mid + <span class="hljs-number">1</span>;
        <span class="hljs-keyword">else</span>
            right = mid - <span class="hljs-number">1</span>;
    }

    <span class="hljs-keyword">return</span> <span class="hljs-number">-1</span>; <span class="hljs-comment">// 目標未找到</span>
}
</code></div></div></pre>

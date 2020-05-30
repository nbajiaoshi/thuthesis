---


---

<h2 id="implement-generic-undoredo">Implement Generic Undo/Redo</h2>
<p>Your task is to implement the following three functions to enable undo/redo functionality with a maximum of 100 undos:</p>
<ul>
<li><code>doAction(action: Function, inverseAction: Function)</code></li>
<li><code>undo()</code></li>
<li><code>redo()</code></li>
</ul>
<p>Whenever the user attempts to execute an action, the <code>doAction</code> function will be called and will be<br>
provided with two parameters, the first being a <code>Function</code> that will commit the intended action when<br>
called, and the second being a <code>Function</code> that will commit the inverse of the intended action (undoes it)<br>
when called.</p>
<p>The <code>undo</code> and <code>redo</code> functions are intended to function similar to their implementations in most<br>
applications. Watch out for edge cases. Make sure you limit the number of possible undos to 100<br>
(so if the users executes 115 actions, the first 15 actions should not be undoable).</p>
<p>This is intended to be web frontend exercise, so please use JavaScript. You may create global variables.<br>
You can use any modern JavaScript features up to ES2019. Using external libraries is not allowed. We will<br>
be reading your code so don’t worry about silly mistakes as long as you have the overall idea.</p>
<p>Example usage (note that this is just an example and does not cover all functionality or edge cases):</p>
<pre class=" language-javascript"><code class="prism  language-javascript"><span class="token keyword">function</span> <span class="token function">main</span><span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  <span class="token keyword">let</span> count <span class="token operator">=</span> <span class="token number">0</span><span class="token punctuation">;</span>

  <span class="token keyword">const</span> <span class="token function-variable function">add5</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> count <span class="token operator">+=</span> <span class="token number">5</span><span class="token punctuation">;</span>
  <span class="token keyword">const</span> <span class="token function-variable function">add5Inverse</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> count <span class="token operator">-=</span> <span class="token number">5</span><span class="token punctuation">;</span>

  <span class="token keyword">const</span> <span class="token function-variable function">subtract2</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> count <span class="token operator">-=</span> <span class="token number">2</span><span class="token punctuation">;</span>
  <span class="token keyword">const</span> <span class="token function-variable function">subtract2Inverse</span> <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> count <span class="token operator">+=</span> <span class="token number">2</span><span class="token punctuation">;</span>

  <span class="token function">doAction</span><span class="token punctuation">(</span>add5<span class="token punctuation">,</span> add5Inverse<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token function">doAction</span><span class="token punctuation">(</span>subtract2<span class="token punctuation">,</span> subtract2Inverse<span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token function">doAction</span><span class="token punctuation">(</span>add5<span class="token punctuation">,</span> add5Inverse<span class="token punctuation">)</span><span class="token punctuation">;</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>count<span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// should print 8</span>

  <span class="token function">undo</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token function">undo</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>count<span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// should print 5</span>

  <span class="token function">redo</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span>count<span class="token punctuation">)</span><span class="token punctuation">;</span> <span class="token comment">// should print 3</span>
<span class="token punctuation">}</span>
</code></pre>


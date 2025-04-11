---
date : 2025-04-11
title: this指针
subtitle: 
draft: false
pin: false
categories: []
---
当类的成员函数被调用时，`this` 指针会被自动传递给该函数。

`this` 指针的类型是 `const Type* const`，它是一个只读指针，指向当前对象。

不能修改 `this` 指针的值，但可以通过 `this` 访问对象的成员。

## 空指针调用

=== "空指针调用不访问this的成员函数"  
	```cpp
	#include<iostream>
	using namespace std;

	class A {
	public:
		void Print() {
			cout << "A::Print()" << endl;
		}
	private:
		int _a;
	};

	int main() {
		A* p = nullptr;
		p->Print();  // 能否正常运行？
		return 0;
	}
	```
	<iframe width="800px" height="400" src="https://godbolt.org/e?readOnly=true&hideEditorToolbars=true#g:!((g:!((g:!((h:codeEditor,i:(filename:'1',fontScale:14,fontUsePx:'0',j:1,lang:c%2B%2B,selection:(endColumn:1,endLineNumber:18,positionColumn:1,positionLineNumber:18,selectionStartColumn:1,selectionStartLineNumber:18,startColumn:1,startLineNumber:18),source:'%23include%3Ciostream%3E%0Ausing+namespace+std%3B%0A%0Aclass+A+%7B%0Apublic:%0A++++void+Print()+%7B%0A++++++++cout+%3C%3C+%22A::Print()%22+%3C%3C+endl%3B%0A++++%7D%0Aprivate:%0A++++int+_a%3B%0A%7D%3B%0A%0Aint+main()+%7B%0A++++A*+p+%3D+nullptr%3B%0A++++p-%3EPrint()%3B++//+%E8%83%BD%E5%90%A6%E6%AD%A3%E5%B8%B8%E8%BF%90%E8%A1%8C%EF%BC%9F%0A++++return+0%3B%0A%7D%0A'),l:'5',n:'0',o:'C%2B%2B+source+%231',t:'0')),k:47.903822441430336,l:'4',n:'0',o:'',s:0,t:'0'),(g:!((h:executor,i:(argsPanelShown:'0',compilationPanelShown:'0',compiler:vcpp_v19_latest_x64,compilerName:'',compilerOutShown:'0',execArgs:'',execStdin:'',fontScale:14,fontUsePx:'0',j:1,lang:c%2B%2B,libs:!(),options:'',overrides:!((name:stdver,value:c%2B%2B17)),runtimeTools:!(),source:1,stdinPanelShown:'1',tree:'1',wrap:'1'),l:'5',n:'0',o:'Executor+x64+msvc+v19.latest+(C%2B%2B,+Editor+%231)',t:'0')),header:(),k:52.096177558569664,l:'4',m:100,n:'0',o:'',s:0,t:'0')),l:'2',n:'0',o:'',t:'0')),version:4"></iframe>

	:material-numeric-1: 当调用 `p->Print()` 时，`this` 指针实际上等于 `nullptr`，但由于 `Print()` 函数没有访问任何成员变量，因此C++允许这个调用。

	:material-numeric-2: `this` 指针是隐含的，虽然在函数内部会传递 `this`，但是如果成员函数不访问任何成员变量，C++不需要解引用这个空指针，因此不会出现空指针访问的错误。
=== "空指针调用访问this的成员函数"
	```cpp
	#include<iostream>
	using namespace std;

	class A {
	public:
		void Print() {
			cout << "A::Print()" << endl;
			cout << _a << endl;
		}
	private:
		int _a;
	};

	int main() {
		A* p = nullptr;
		p->Print();  // 能否正常运行？
		return 0;
	}
	```
	<iframe width="800px" height="400px" src="https://godbolt.org/e?readOnly=true&hideEditorToolbars=true#g:!((g:!((g:!((h:codeEditor,i:(filename:'1',fontScale:14,fontUsePx:'0',j:1,lang:c%2B%2B,selection:(endColumn:14,endLineNumber:17,positionColumn:14,positionLineNumber:17,selectionStartColumn:14,selectionStartLineNumber:17,startColumn:14,startLineNumber:17),source:'%23include%3Ciostream%3E%0Ausing+namespace+std%3B%0A%0Aclass+A+%7B%0Apublic:%0A++++void+Print()+%7B%0A++++++++cout+%3C%3C+%22A::Print()%22+%3C%3C+endl%3B%0A++++++++cout+%3C%3C+_a+%3C%3C+endl%3B%0A++++%7D%0Aprivate:%0A++++int+_a%3B%0A%7D%3B%0A%0Aint+main()+%7B%0A++++A*+p+%3D+nullptr%3B%0A++++p-%3EPrint()%3B++//+%E8%83%BD%E5%90%A6%E6%AD%A3%E5%B8%B8%E8%BF%90%E8%A1%8C%EF%BC%9F%0A++++return+0%3B%0A%7D%0A'),l:'5',n:'0',o:'C%2B%2B+source+%231',t:'0')),k:50,l:'4',n:'0',o:'',s:0,t:'0'),(g:!((h:executor,i:(argsPanelShown:'0',compilationPanelShown:'0',compiler:vcpp_v19_latest_x64,compilerName:'',compilerOutShown:'0',execArgs:'',execStdin:'',fontScale:14,fontUsePx:'0',j:1,lang:c%2B%2B,libs:!(),options:'',overrides:!((name:stdver,value:c%2B%2B17)),runtimeTools:!(),source:1,stdinPanelShown:'1',tree:'1',wrap:'1'),l:'5',n:'0',o:'Executor+x64+msvc+v19.latest+(C%2B%2B,+Editor+%231)',t:'0')),header:(),k:50,l:'4',n:'0',o:'',s:0,t:'0')),l:'2',n:'0',o:'',t:'0')),version:4"></iframe>
	
	:material-numeric-1: 当 `this` 指针为 `nullptr` 时，访问 `this->_a` 等同于尝试通过空指针访问成员变量。这是一种未定义行为，在大多数系统中会导致程序崩溃。

	:material-numeric-2: 成员变量 `_a` 存储在对象的内存空间中，而通过空指针访问成员变量时，由于没有实际的对象空间可用，因此程序在运行时会发生崩溃。

!!! abstract "空指针调用成员函数"
	总结来说，**空指针调用成员函数本身并不会报错** ，因为成员函数本来就不在类中，所以不是解引用，编译时的汇编代码这里就只是一段函数的地址而已，只是这里没有对象，传过去的 `this` 指针就是空指针，但只要该成员函数不涉及访问成员变量或其他依赖对象内存的操作那就不会报错。
	
	然而，一旦成员函数试图通过 `this` 指针访问成员变量，程序就会崩溃，因为 `this` 为 `nullptr`，没有有效的内存空间可供访问。
## this指针存放位置

`this` 指针作为成员函数的一个隐含参数，存储在栈中。每当一个成员函数被调用时，`this` 指针会作为函数参数被压入栈中。



> this指针其实就是函数的参数而已

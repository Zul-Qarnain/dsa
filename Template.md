Function Template = describes what a function looks like.
				   Can be used to generate as many overloaded function as needed,each using different data types.

For example: 
```cpp
#include<iostream>
int max(int a,int b){
	return(a>b)? a:b;
}
char max(char a,char b){
	return(a>b)? a:b;
}
double max(double a,double b){
	return(a>b)? a:b;
}

int main(){
	std::cout<< max(1,1)<<"\n";
}
```
But instead of writing this code many times . We can just write the template of this codes so that we don't need to over write the same thing . Here is the example:
```cpp
#include<iostream>

template<typename T>

T max(T a,T b){
	return(a>b) ? a:b;
}
int main(void){
	std::cout<<max(3,4)<<"\n";
}
```
Again for the multiple for different types of parameter we can write the template too. Here is the another example:
```cpp
#include<iostream>

template<typename T,typename U>

auto max(T a,U b){
	return(a>b) ? a:b;
}
int main(void){
	std::cout<<max(3,4)<<"\n";
}
```
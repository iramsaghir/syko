# syko

import SwiftUI

struct ContentView: View {
    @State var email = ""
    @State var password = ""
    @State private var isActive = false
    

    var body: some View {
        
        NavigationView {
            VStack(spacing : 15){
                Spacer()
                HStack{
                    Image(systemName: "envelope")
                        .foregroundColor(.green)
                    TextField("Email", text:$email)
                }//.frame(height: 60)
                .padding(.all,20)
                .background(Color.gray)
                .cornerRadius(8)
                .padding(.horizontal,20)
                HStack{
                    Image(systemName: "lock")
                        .foregroundColor(.green)
                    SecureField("password", text:$password)
                }//.frame(height: 60)
                .padding(.all,20)
                .background(Color.gray)
                .cornerRadius(8)
                .padding(.horizontal,20)
                NavigationLink(destination:
                CreateView() ,isActive: $isActive){
                Button(action: {
                    isActive = true
                })
                {
                    Text("Login")
                        .foregroundColor(.white)
                        .font(.system(size: 24,weight: .medium))
                }.frame(maxWidth: .infinity)
                .padding(.vertical,20)
                .background(Color.green.opacity(0.8))
                .cornerRadius(8)
                .padding(.horizontal,20)
                Spacer()
                Spacer()
                }
            }.background(
                Image("syko5")
                    .resizable()
                    .aspectRatio(contentMode: /*@START_MENU_TOKEN@*/.fill/*@END_MENU_TOKEN@*/)
            ).edgesIgnoringSafeArea(/*@START_MENU_TOKEN@*/.all/*@END_MENU_TOKEN@*/)
        }
    }
}
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        Group{
            //ContentView().preferredColorScheme(.light).previewDevice("iphone 11")
            
        }
    }
}

using System.Text;
using System.Threading.Tasks;
using System.Runtime.Remoting;
using System.Runtime.Remoting.Channels;
using System.Runtime.Remoting.Channels.Tcp;
using Dll;
namespace server
{
    class Program
    {
        static void Main(string[] args)
        {
            TcpServerChannel channel = new TcpServerChannel(3128);
            ChannelServices.RegisterChannel(channel);
            RemotingConfiguration.RegisterWellKnownServiceType(typeof(Class1), "Hello", WellKnownObjectMode.SingleCall);
            Console.WriteLine("press Entar to stop server");
            Console.ReadLine();
        }
    }
}
